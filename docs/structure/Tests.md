# Tests

Put here the description in how to test each module of you application.

For example split in sections each part of the application and how the team wants to test it:

## Components

```typescript jsx
// src/modules/foo/components/SomeComponent/__mocks__/index.tsx
import React from 'react';
import {ProviderProps} from '../../../../../core';
import buildMockComponent from '../../../../../core/test-utils/buildMockComponent';

export const Mock = jest.fn();
export const Implementation = ({children}: ProviderProps) => <div data-testid="some-component">{children}</div>;

export default buildMockComponent<ProviderProps>(Mock, Implementation);

// src/modules/foo/component/SomeDependentComponent/SomeDependentComponent.spec.tsx
// ...
jest.mock('../SomeComponent');
// ...
it('should use the manual mock', () => {
   result = render(<SomeDependentComponent />);
   expect(result.queryByTestId('some-component')).toBeTruthy();
});

it('should expose the Jest mock instance', () => {
  expect(jest.requireMock('../SomeComponent')).toHaveProperty('Mock');
});

it('should expose the mock default implementation', () => {
  expect(jest.requireMock('../SomeComponent')).toHaveProperty('Implementation');
});
```

## Hooks
The RTL exposes some useful functions to test React hooks in a proper environment. The react-hooks package exposes a renderHook function to properly execute a hook in a controlled environment.
 ```tsx
 // hooks/useCounter/useCounter.ts
import {useCallback, useState} from 'react';

export interface Counter {
    value: number;
    increment: () => void;
}

export default () => {
    const [value, setValue] = useState(0);

    const increment = useCallback(() => setValue((previousValue) => previousValue + 1), []);

    return {value, increment};
};

// hooks/useCounter/index.ts
export {default} from './useCounter';
export type {Counter} from './useCounter';

// hooks/useCounter/useCounter.spec.ts
import {renderHook, act, RenderResult} from '@testing-library/react-hooks';
import useCounter, {Counter} from '.';

describe('useCounter', () => {
    let result: RenderResult | null = null;

    const renderUseCounter = () => {
        ({result} = renderHook(() => useCounter()));
    };

    const incrementCounter = () => {
        act(() => {
            result?.current.increment();
        });
    };

    afterEach(() => {
        result = null;
    });

    describe('when using the hook', () => {
        beforeEach(renderUseCounter);

        it('should not have thrown', () => {
            expect(result?.error).toBeFalsy();
        });

        it('should expose the value 0', () => {
            expect(result?.current.value).toBe(0);
        });

        describe('when incrementing', () => {
            beforeEach(incrementCounter);

            it('should expose the value 1', () => {
                expect(result?.current.value).toBe(1);
            });
        });
    });
});
```

And you can have many examples you want like: APIs, Core, UI e etc..
