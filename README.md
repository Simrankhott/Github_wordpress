# WordPress Deployment with Nginx and GitHub Actions

This repository contains the setup for deploying a WordPress website using the Nginx web server, LEMP stack, and GitHub Actions for continuous deployment.

## Table of Contents

- [Introduction](#introduction)
- [Setup](#setup)
  - [Server Provisioning](#server-provisioning)
  - [GitHub Actions Workflow](#github-actions-workflow)
- [Usage](#usage)
- [Configuration](#configuration)
- [Optimizations](#optimizations)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project demonstrates the automated deployment of a WordPress website using Nginx, the LEMP stack (Linux, Nginx, MySQL, PHP), and GitHub Actions for continuous deployment.

## Setup

### Server Provisioning

- Provisioned a Virtual Private Server (VPS) with a secure Linux distribution (e.g., Ubuntu 22.04).
- Configured Nginx as the web server, MySQL/MariaDB as the database, and PHP for processing dynamic content.

### GitHub Actions Workflow

- Created a GitHub Actions workflow (`main.yml`) for automated deployment.
- The workflow triggers on push events to the `main` branch.
- The workflow performs the following steps:
  - Checks out the repository.
  - Installs necessary dependencies and services (mariadb-server, nginx, php, etc.).
  - Downloads and extracts the latest WordPress version.
  - Configures the MySQL/MariaDB database and user.
  - Copies and configures the `wp-config.php` file.
  - Restarts Nginx for the changes to take effect.

## Usage

1. Make changes to your WordPress website locally.
2. Commit and push changes to the `main` branch.
3. GitHub Actions workflow will automatically deploy changes to the VPS.
4. Access your WordPress website via the VPS IP address.

## Configuration

- To configure the MySQL/MariaDB database, modify the `wp-config.php` file.
- SSL/TLS certificates were implemented using Let's Encrypt for secure communication.
- Nginx server configuration was optimized for enhanced website performance.

## Optimizations

- Implemented SSL/TLS certificates using Let's Encrypt for secure communication.
- Optimized Nginx server configuration:
  - Enabled caching and gzip compression for better performance.
  - Tweaked PHP and FastCGI settings for optimal PHP processing.

## Contributing

Contributions are welcome! If you find any issues or improvements, please feel free to create a pull request or submit an issue.

## License

This project is licensed under the [MIT License](LICENSE).
