# Project: ASP.NET Core API project hosted on GitHub along with code analysis using SonarCloud.
Dependency: curl Dependency, Authentication Token .
# CI/CD: Build Automation, Package Generation, Package Publishing and Download Automation.

1.  Trigger:--> This workflow is triggered on pushes to the main branch and pull requests targeting the main branch.
   
# Jobs:
2.  build:--> This job runs on an Ubuntu environment.
3.  Steps:-->
# Checkout: Checks out the repository's code.
# Setup .NET: Sets up the .NET environment using the specified version.
# Restore dependencies for Api project: Restores NuGet dependencies for the API project.
# Build Api project: Builds the API project.
# Test Api project: Runs tests for the API project.
# Generate NuGet packages: Packs the API project into NuGet packages and stores them in the 'nupkgs' directory.
# Publish package: Publishes the generated NuGet packages to a NuGet package source. (It uses an API key stored in GitHub secrets for authentication)
# Download NuGet packages from GitHub package registry: This step attempts to download a NuGet package from the GitHub package registry using curl. It downloads a specific version of the package, AspNetCoreAPI-GitHubAction.Api.1.0.1.nupkg, from the repository pravesh-77/DotNet-WF at version 1.0.1.

4. The curl command below will provide to download the NuGet package from the GitHub package registry to your local machine:-->
   # curl -LJO https://github.com/pravesh-77/DotNet-WF/packages/1.0.1/download/DotNet-WF/1.0.1/AspNetCoreAPI-GitHubAction.Api.1.0.1.nupkg
   Note: Please change the version to get the package in the file name/location: AspNetCoreAPI-GitHubAction.Api.csproj in src.

# In short:
 This workflow automates the (build), (test), (packaging), and (publishing processes for a .NET project), specifically targeting an API project. Additionally, it seems to have a step for downloading a specific version of a NuGet package from a GitHub package registry, possibly for further usage or validation purposes.





























