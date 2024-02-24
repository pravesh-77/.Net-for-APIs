# Project Overview:
Project Type: ASP.NET Core API project hosted on GitHub
Code Analysis: Integrated SonarCloud for code analysis
Dependencies: Utilizes curl dependency and requires an Authentication Token
CI/CD Automation: Implements Build Automation, Package Generation, Package Publishing, and Download Automation

# Workflow Details:-->
1. Trigger:
Workflow triggered on pushes to main branch and pull requests targeting main branch.

2. Jobs:
build:

3. Environment: Ubuntu
   
4. Steps:
Checkout repository code.
Setup .NET environment.
Restore NuGet dependencies for API project.
Build API project.
Test API project.
Generate NuGet packages.
Publish NuGet packages to a package source using an API key.
Download a specific version of a NuGet package from GitHub package registry using curl.

# Additional Note:
The provided curl command allows downloading a specific NuGet package version from the GitHub package registry:
  curl -LJO https://github.com/pravesh-77/DotNet-WF/packages/1.0.1/download/DotNet-WF/1.0.1/AspNetCoreAPI-GitHubAction.Api.1.0.1.nupkg
  PS: PLease change the version in AspNetCoreAPI-GitHubAction.Api.csproj file in src project's folder.

# Summary:
This GitHub Actions workflow automates the entire CI/CD pipeline for an ASP.NET Core API project hosted on GitHub. It encompasses building, testing, packaging, publishing, and even includes a step for downloading specific NuGet packages for further usage or validation. The integration with SonarCloud ensures code quality and security analysis throughout the process. One can Deploy an ASP.NET artifact on IIS to host the application ensuring runtime dependencies are installed, along with the application's reliability and performance.
