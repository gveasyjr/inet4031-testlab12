# Docker Lab: Containerizing a Three-Tier Application
**INET 4031 - Introductions to Systems**

This lab introduces Docker and Docker Compose by having you containerize a
real, multi-service application. You will package three components: Apache,
Flask, and MariaDB. These will be packaged into separate containers and wired together so they function as a complete application.

The application code and scaffolding are provided. Your job is to complete the Dockerfiles, verify the stack runs correctly, and document your work below.

> **Directions and explanations for this lab are on the repository Wiki.**
> Refer to the Wiki pages for step-by-step instructions.

---

*The sections below are for you to fill out. Replace each placeholder with your own content before submitting. Having a detailed README is the best practice for showing your work in future GitHub repositories.*

---

# Project Overview
This application is a simple web‑based ticketing system that lets users submit and view support tickets in one place. It solves the problem of not having a centralized system to track issues by storing tickets in a database and exposing them through a web interface. The user interacts with the “Docker Lab – Ticketing System” webpage, where they can see existing tickets, check API health, and create new tickets through the form.

<!-- Briefly describe what this application does in your own words.
     What problem does it solve? What does a user interact with? -->

# Prerequisites
You must be running an Ubuntu 64‑bit VM with at least 2 GB of RAM and 2 CPU cores. Docker and Docker Compose must be installed and working, and your user must be added to the docker group so Docker commands can run without sudo. The VM also needs the components used inside the containers: Apache, MariaDB, and Flask, which will be installed automatically when their Docker images are built.

<!-- List what needs to be installed or configured on the VM before this lab
     will work. Include Docker, Docker Compose, and anything else required. -->

# Getting Started
create a environment file "cp .env.example .env"

<!-- Explain how a new teammate would bring this stack up from a fresh clone.
     Walk through every command they need to run, in order. -->

# Configuration
A new teammate should begin by cloning the repository and moving into the project directory. After that, they must create their own environment file by running: cp .env.example .env
Once the .env file is created and filled in, they can start the stack by running: docker compose up --build
This will build the images, start all three services, and bring the application online.

<!-- Explain the .env file: what it is, what variables it contains,
     and what a teammate needs to provide that is not in this repository. -->

# Verification
To confirm the stack is running correctly, first check that the db and app containers show a healthy status using docker compose ps, while the web container shows running. Next, verify that the frontend loads by visiting http://<your‑VM‑IP>:80 and confirming the dashboard displays a green “API healthy” indicator and the seed ticket. You should also confirm that the health endpoint works through Apache by running curl http://localhost:80/health and that the API returns ticket data from the database. Once all manual checks pass, run the provided check-lab.sh script; a passing run will show all tests marked as PASS with no failures.

<!-- Describe how to confirm the stack is running correctly.
     Reference the check script and what a passing run looks like. -->

