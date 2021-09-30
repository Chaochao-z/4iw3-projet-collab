# How to contribute

## Writing Code
You need to follow the classical guideline and conventions when writing Laravel on this project. We highly recommend to have a linter so your code can pass our pipeline.

## Commit naming
Commits have to be named using this schema :
```
feat: add user route 
^--^  ^------------^
|     |
|     +-> Summary in present tense.
|
+-------> Type: chore, docs, feat, fix, refactor, style, or test.
```

### More Examples:

- `feat`: (new feature for the user, not a new feature for build script)
- `fix`: (bug fix for the user, not a fix to a build script)
- `docs`: (changes to the documentation)
- `style`: (formatting, missing semi colons, etc; no production code change)
- `refactor`: (refactoring production code, eg. renaming a variable)
- `test`: (adding missing tests, refactoring tests; no production code change)
- `chore`: (updating grunt tasks etc; no production code change)


## Submitting Patches
When you are ready to submit a bug fix you will need 1 reviwer to validate your code. Then you will be able to merge your patch into the develop branch.

## Merging Pull Requests
You can only merge if your MR has been reviewed and the pipeline has passed.
