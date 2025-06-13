# LureKit

<p align="center">
  <img src="https://raw.githubusercontent.com/JonnyPake/LureKit/refs/heads/main/images/LureKitLogo.png" alt="lurekit" width="450" height="450"/>
</p>

LureKit is a modern phishing infrastructure toolkit that helps you quickly deploy, manage, and destroy phishing environments for internal security assessments, social engineering simulations, and campaign testing - providing the ability to send phishing emails, serve branded landing pages, and collect credentials in a simple easy to use script.

# What It Does

- Sends phishing emails using Mailgun via SMTP
- Deploys GoPhish backend on a clean VPS
- Deploys NGINX redirector with TLS and region-based filtering (optional)
- Supports multiple client subdomains like login.company.co.uk, mail.portalsite.net
- Uses Cloudflare for DNS management (can used other hosting providers)
- Can be taken offline/pointed to benign pages easily to protect domain reputation
- Designed to avoid detection and indexing by scanners (GeoIP, bot filters, anti-crawler rules)

# Basic Workflow

- Clone the repo and configure environment variables
- Run the `gophish-deploy.sh` script on your GoPhish VPS
- Run the `redirector-deploy.sh` script on your NGINX redirector VPS
- Configure DNS for `phish.yourdomain.com` and `login.yourdomain.com`
- SSH tunnel into GoPhish admin panel for management
- Launch campaign, collect results
- Destroy infra or take it offline to preserve domain

# Requirements

A couple of requirements are necessary for this to run:

- Managed domain (e.g., yourdomain.co.uk)
- VPS 1: GoPhish backend (e.g., phish.yourdomain.co.uk)
- VPS 2: Redirector for TLS + phishing page (e.g., login.yourdomain.co.uk)
- A Mailgun account and verified domain with working SMTP
- Linux system (Ubuntu 20.04 or 22.04 preferred)

