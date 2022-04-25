# bisectable_buggery
Fabricated history simulating parallell feature development

## Bisect to find which commit intruduced a bug:
Git bisect uses a binary search to help you find an evil comit ASAP.

### Setup:
- Checkout a commit where the bug exists (e.g. the final comit if debugging feature 4)
- ```git bisect start``` to start the process
- ```git bisect bad``` to define one end of the binary search
- ```git bisect good ###``` with ### as a commit where the bug did not exist (e.g. ```33204cb9```, the first commit)


### The cycle:
The bisector will now checkout a new commit and you need to tell it if this is a good commit where the bug does not exist or a bad one where it does:

```git bisect good``` or ```git bisect bad```

The cycle should end on the commit that introduced the bug.

I'm told it's possible to automate the good/bad feedback with tests.