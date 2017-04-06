# Purpose

Provide a local development environment for the Lumen PBJ application.

# Requirements

- Docker 17.03
- Pantheon config file

If you are on a Mac, you will need to use the newer "Docker for Mac" instead of
"Docker Toolbox".

# Pantheon config file

Log into Pantheon and obtain the repo URL for PBJ.

Click:
1. Organizations
1. Lumen Learning
1. "Sites" tab
1. "candela" link
1. "Connection Info" button
1. Copy the "SSH clone URL" string

Create a file on your laptop, in a terminal window with:

	$ mkdir -p ~/.pantheon
	$ echo 'candela_git_url=<SSH clone URL here>' > ~/.pantheon/candela_config.ini

# Installation

## Step 1: Install Docker

You will need to download and install Docker.

- [https://www.docker.com/products/docker](https://www.docker.com/products/docker)

## Step 2: Build and start the PBJ development environment

This will build the Docker images and containers used to serve run project.

	$ cd ~/pbj-docker
	$ ./start-everything.sh

The first time this command is used, it will take a while to complete. It will be downloading
several Debian packages for the various server-side dependencies required by PBJ.

## Step 3: Enjoy!

Your project files are now located in: `~/Sites/pbj`
Your database files are located in: `~/Sites/pbj-db`

Your Wordpress website is reachable at: [http://localhost:8081/](http://localhost:8081/)

If you need to connect directly to the database, it will be available at localhost:3307.