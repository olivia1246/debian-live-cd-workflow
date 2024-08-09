# Debian Live CD Custom Build Workflow

Currently is only for x86/i686 machines. It should boot on x86_64/amd64 however the operating system is only for x86 machines at this time. May make an update to allow native amd64 building.

## Overview

This repository provides a GitHub Actions workflow to automate the creation of a customized Debian Live CD ISO. The workflow is designed to build a Debian Live ISO from scratch, including installing packages, configuring the environment, and generating the final ISO image.

## Features

- **Automated Builds**: Triggers on push to the `main` branch or monthly at midnight UTC.
- **Manual Triggers**: Allows manual execution from the GitHub Actions UI.
- **Customizable**: Easy to add or remove packages to tailor the Live CD image to your needs.

## Workflow

The workflow includes the following steps:

1. **Checkout Repository**: Fetches the latest code from the repository.
2. **Set Up Prerequisites**: Installs necessary tools and dependencies.
3. **Create Build Directory**: Prepares the directory structure for the build.
4. **Bootstrap Debian Bullseye**: Sets up a basic Debian environment.
5. **Install Packages**: Adds the Linux kernel, live-boot tools, and other specified packages.
6. **Configure Live Environment**: Prepares the filesystem, kernel, and boot configurations.
7. **Create ISO**: Compiles the final ISO image and uploads it as an artifact.

## How to Add Custom Packages

1. **Fork the Repository**: Start by forking this repository to make your modifications.
2. **Locate the Workflow**: Navigate to `.github/workflows/main.yml`.
3. **Find the "Install packages" Line**: This line is currently at line 39 and has a comment next to it.
4. **Modify Packages**: Add or remove packages on line 42. Be careful not to delete anything else important to avoid errors.
5. **Commit Changes**: Commit your modified `main.yml` file to your fork. This will automatically start creating your ISO.
