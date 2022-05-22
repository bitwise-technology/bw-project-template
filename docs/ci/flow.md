Example in how to represent the CI Flow:

```
 Install dependencies          ---> Cache "node_modules" folder
          |
          V
  Lint + Unit tests
         / \
        /   \
  Generate   Build staging     ---> If on "master" branch
  Artifacts. Build production  ---> If a tag is associated on the commit
```
