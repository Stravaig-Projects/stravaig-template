# stravaig-template

## TO DO

When starting with this template the following needs to be updated:

* Rename files:
  * Rename file `/src/Stravaig.XXXX.sln` (XXXX = name of the solution within the `Stravaig` namespace)
  * Rename file `/src/Stravaig.XXXX.sln.DotSettings` (XXXX = name of the solution within the `Stravaig` namespace)
  * Rename folder `/src/.idea/.idea.XXXX` (XXXX = name of solution without the file extension)
* Add project files
  * Add the initial main project that will be packaged and tests to the solution.
  * Move the `/src/stravaig-icon.png` file into the package project folder.
  * Update the main project `.csproj` file with the details in the "package details" (below)
* Update the `.github/workflows/build.yml` file with
  * The name of the project (line 1)
  * The environment variables in `jobs` \ `build` \ `env` to point to the new solution project and tests

## Package Details

This should be added to the main `.csproj` file:

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <StravaigBuildTime>$([System.DateTime]::Now.ToString("dddd, d MMMM yyyy 'at' HH:mm:ss zzzz"))</StravaigBuildTime>
        <StravaigCopyrightYear>$([System.DateTime]::Now.ToString("yyyy"))</StravaigCopyrightYear>
        <StravaigGitHubCommit>$(GITHUB_SHA)</StravaigGitHubCommit>
        <StravaigWorkflowUrl>$(GITHUB_SERVER_URL)/$(GITHUB_REPOSITORY)/actions/runs/$(GITHUB_RUN_ID)</StravaigWorkflowUrl>
    </PropertyGroup>

    <PropertyGroup>
        <YEAR>$([System.DateTime]::Now.Year)</YEAR>
        <TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>
        <Title>Stravaig XXXX</Title>
        <Authors>Colin Angus Mackay</Authors>
        <Copyright>©2020-$(StravaigCopyrightYear) Stravaig Projects. See licence for more information.</Copyright>
        <PackageProjectUrl>https://github.com/$(GITHUB_REPOSITORY)/blob/$(StravaigGitHubCommit)/README.md</PackageProjectUrl>
        <PackageLicenseExpression>MIT</PackageLicenseExpression>
        <RepositoryUrl>https://github.com/Stravaig-Projects/XXXX</RepositoryUrl>
        <PackageIcon>stravaig-icon.png</PackageIcon>
        <PackageTags>XXXX</PackageTags>
        <GenerateDocumentationFile>true</GenerateDocumentationFile>
        <Description>XXXX.
        
Built on $(StravaigBuildTime).
Build run details at: $(StravaigWorkflowUrl)
        </Description>
    </PropertyGroup>

    <ItemGroup>
        <None Include="stravaig-icon.png" Pack="true" PackagePath="/" />
    </ItemGroup>

    <!-- Other things here -->
</Project>
```

Any part with `XXXX` should be replaced with appropriate information.
