# Documentation pipeline
> Credit goes to Shay Rojansky for writing a tutorial on connecting DocFX with the GitHub Actions platform at http://www.roji.org/docfx-with-github-actions. Thank you!

This repository creates an automated documentation pipeline for Camphora's .NET libraries.

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
