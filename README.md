
# Project Title

A brief description of what this project does and who it's for

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
- [API Reference](#api-reference)
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

## API Reference

Configure your Nginx server block to handle PHP requests and include `index.php` in the list of index files:

```
# Add index.php to the list if you are using PHP
index index.php index.html index.htm index nginx-debian.html;
```

```nginx
location ~ \.php$ {
    include snippets/fastcgi-php.conf;

    # With php-fpm (or other unix sockets):
    fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;
    # With php-cgi (or other tcp sockets):
    # fastcgi_pass 127.0.0.1:9000;
}

## Screenshots

<p align="center">
  <img width="960" alt="wp-1" src="https://github.com/Simrankhott/Github_wordpress/assets/91006102/92d377d2-f718-4515-a827-8cc958f77d19">
</p>


<br>

<p align="center">
  <img width="960" alt="wp-2" src="https://github.com/Simrankhott/Github_wordpress/assets/91006102/6a61d0f3-8669-4cd1-a6ef-0bbbed2caf99">
</p>


<br>

<p align="center">
  <img width="960" alt="wp-4" src="https://github.com/Simrankhott/Github_wordpress/assets/91006102/b42d19f0-c9bf-4a9f-957f-acb78d93bbe3">
</p>


<br>

<p align="center">
  <img width="960" alt="wp-5" src="https://github.com/Simrankhott/Github_wordpress/assets/91006102/0270df6f-d1b0-41cf-b68b-29aad550b02f">
</p>


<br>

<p align="center">
  <img width="960" alt="wp-6" src="https://github.com/Simrankhott/Github_wordpress/assets/91006102/a514c534-5990-4a01-b10f-baf1830826c2">
</p>


<br>

<p align="center">
  <img width="960" alt="wp-7" src="https://github.com/Simrankhott/Github_wordpress/assets/91006102/5995bff8-5744-4ae1-b01a-61b27eb4acc9">
</p>


<br>

<p align="center">
  <img width="960" alt="wp-8" src="https://github.com/Simrankhott/Github_wordpress/assets/91006102/4419f764-f369-41bb-b031-cb739898b02f">
</p>









