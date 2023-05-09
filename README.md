# Documentation CI pipeline for C# projects

> Credit goes to Shay Rojansky for writing a tutorial on connecting DocFX with the GitHub Actions platform at http://www.roji.org/docfx-with-github-actions. Thank you!

This repository creates an automated documentation pipeline by building a single DocFX website from multiple C# repositories. While I don't write in C# as nearly as often as I used to, I'd like to share this with others in case others would also like to use it!

## Process
1. Each library sends a repository dispatch event through a GitHub Actions workflow after every time a commit is pushed to master.
2. This repository listens for the repository dispatch event.
3. This repository runs a GitHub Actions workflow for building documentation, through the following steps:
	1. Check out this repository
	3. Check out repository to place the documentation
	2. Check out repositories to build documentation for
	4. Install .NET Core
	5. Install Mono
	6. Download DocFX
	7. Build documentation with DocFX
	7. Commit changes and push

## Files
 - [`./.github/build-documentation.yml`](./.github/build-documentation.yml): A CI workflow written in GitHub Actions.
 - `./conceptual/{project}/index.md`: A Markdown file that represents the homepage of that specific project.
 - `./conceptual/{project/toc.md`: A Markdown file that represents the Table of Contents of that specific project.
 - [`./docfx.json`](./docfx.json) ([docs](https://dotnet.github.io/docfx/reference/docfx-json-reference.html)): The configuration file for DocFX.
 - [`./toc.yml`](./toc.yml) ([docs](https://dotnet.github.io/docfx/docs/table-of-contents.html)): A high-level Table of Contents for DocFX.

## Tools
 - **DocFX** ([Docs](https://dotnet.github.io/docfx/index.html) • [GitHub](https://github.com/dotnet/docfx)): A static site generator for C#/.NET API documentation.
 - **GitHub Actions** ([Docs](https://docs.github.com/en/actions)): A platform for integrating CI/CD (continuous integration/continuous delivery) with repositories.
 - **GitHub Pages** ([Docs](https://docs.github.com/en/pages)): A platform for hosting static websites on GitHub.
 
