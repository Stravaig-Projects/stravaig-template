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
        <YEAR>$([System.DateTime]::Now.Year)</YEAR>
        <TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>
        <Title>Stravaig XXXX</Title>
        <Authors>Colin Angus Mackay</Authors>
        <Description>XXXX.</Description>
        <Copyright>©2020-$(YEAR) Colin Angus Mackay. See licence for more information.</Copyright>
        <PackageProjectUrl>https://github.com/Stravaig-Projects/XXXX/blob/main/README.md</PackageProjectUrl>
        <PackageLicenseExpression>MIT</PackageLicenseExpression>
        <RepositoryUrl>https://github.com/Stravaig-Projects/XXXX</RepositoryUrl>
        <PackageIcon>stravaig-icon.png</PackageIcon>
        <PackageTags>XXXX</PackageTags>
        <GenerateDocumentationFile>true</GenerateDocumentationFile>
    </PropertyGroup>

    <ItemGroup>
        <None Include="stravaig-icon.png" Pack="true" PackagePath="/" />
    </ItemGroup>

    <!-- Other things here -->
</Project>
```

Any part with `XXXX` should be replaced with appropriate information.