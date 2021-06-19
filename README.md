# stravaig-template

## TO DO

When starting with this template the following needs to be updated:

* Rename file `/src/Stravaig.XXXX.sln` (XXXX = name of the solution within the `Stravaig` namespace)
* Rename file `/src/Stravaig.XXXX.sln.DotSettings` (XXXX = name of the solution within the `Stravaig` namespace)
* Rename folder `/src/.idea/.idea.XXXX` (XXXX = name of solution without the file extension)
* Add the initial project and tests to the solution.
* Update the `.github/workflows/build.yml` file with
  * The name of the project (line 1)
  * The environment variables in `jobs` \ `build` \ `env` to point to the new solution project and tests
