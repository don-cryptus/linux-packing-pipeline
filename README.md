# GitHub Pipeline for Publishing Software Packages

This GitHub pipeline is designed to automate the process of building and publishing software packages in multiple formats (DEB, RPM, Arch Linux) for a Node.js project. It is triggered on pushes to the main branch or manually via workflow dispatch.

## Overview

The pipeline consists of two main jobs:

1. **Setup**: Prepares the environment and extracts package information from `package.json`.
2. **Publish-Release**: Builds DEB, RPM, and Arch Linux packages and publishes them as a GitHub release.

### Features

- Automated versioning based on `package.json`.
- Supports x86_64 architecture.
- Creates and publishes DEB, RPM, and Arch Linux packages.
- Removes any existing tags and releases for the current version to ensure uniqueness.

## Prerequisites

- A Node.js project with a valid `package.json` file.
- GitHub repository for the project.

## Usage

1. **Integration**: To integrate this pipeline into your project, add the provided YAML file to your `.github/workflows` directory.

2. **Configuration**: Customize the environment variables and other settings as per your project's requirements.

3. **Triggering the Pipeline**:
   - **Manual Trigger**: Go to the Actions tab of your GitHub repository, select this workflow, and run it manually.
   - **Automatic Trigger**: The pipeline runs automatically on every push to the `main` branch.

## Workflow Steps

### Setup Job

- Checks out the repository code.
- Sets up Node.js environment.
- Extracts and outputs package information from `package.json`.

### Publish-Release Job

- Deletes existing tag and release for the current version.
- Builds the DEB package and prepares it for release.
- Generates a `PKGBUILD` file for Arch Linux package building.
- Creates Arch Linux and RPM packages.
- Calculates checksums for all packages.
- Uploads the packages and checksums to GitHub releases.

## Environment Variables

- `EMAIL`: The email address used in package metadata.
- `ARCH`: Architecture for the packages (default: x86_64).

## Contributing

For any contributions or modifications to this pipeline, please follow your project's contribution guidelines.

## License

Please refer to the project's license as defined in your repository.

---

For more information or support, please refer to the GitHub Actions documentation or raise an issue in this repository.
