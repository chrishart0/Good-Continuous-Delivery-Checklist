# Continuous Delivery Book Notes
Github Pages: <https://chrishart0.github.io/Good-Continuous-Delivery-Checklist/>

## Checklist of everything needed to preform Continuous Delivery:

Based on the Book by Jez Humble and David Farley

### Continuous Integration 

- CI Pipeline
  - Runs on every commit with little or no delay (p55, p63)
  - Notifies you of success or failure (p 63)
  - CI should take about 90 seconds, ideally no more than 5 mins, absolutely no more than 10 mins. ( p 61)
- Developer Environment (p 62)
  - Full build runs on dev machine
  - Same Test which run on CI server run on dev machine
  - 3rd party libraries are version pegged and dev env gets same version that CI build does
  - One sign if a good application architecture is it runs without much trouble on a development machine
- Broken Builds
  - Never go home on a broken build! Either stay and fix it or revent your changes (p 68)
  - If a broken build can't be fixed quickly. Revert it! Then fix locally and re-push. ( p69). You should timebox fixing broken build in CI. (P70)

### Unit testing

-  Never comment out a failing test (p70). If the test is failing, then fix it. If you determine the functionality being tested is no longer needed, either modify the test for the new functionality or delete i.

### Branching:

- Use trunk based development([Read More](https://trunkbaseddevelopment.com/)), no or very minimal use of branches
- Developers should check into the trunk/main line branch as much as several times a day (p 59)
- Before checking in code developers should be in the habit of running all tests and building to ensure the pipeline does not fail when they commit. Local pre-commit process should give reasonable confidence CI will pass. ( p66)
- Don't check in on a broken build, this is a cardinal sin! ( p 66). #1 priority is fixing a broken build, so dev should be working on it and next commit will make it harder.