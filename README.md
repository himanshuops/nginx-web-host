# Setting up Nginx with Let's Encrypt SSL on Docker Compose

## Prerequisites

- Docker
- Docker Compose
- Registered domain name (e.g., `unni.live`)

## Directory Structure
/tset
├── docker-compose.yml
├── html
│ └── index.html
├── nginx
│ ├── conf.d
│ │ └── default.conf
│ └── nginx.conf
└── letsencrypt.


## Instructions

1. **Create HTML File**

```sh
mkdir html
touch html/index.html

Create Docker Compose File

$ VI touch docker-compose.yml


Update Nginx Configuration
Update nginx/conf.d/default.conf:

nano nginx/conf.d/default.conf

Run Certbot to Obtain SSL Certificate

$docker-compose run --rm certbot certonly --webroot --webroot-path=/usr/share/nginx/html --email your-email@example.com --agree-tos --no-eff-email -d unni.live

Restart Docker Compose Services

$docker-compose down
$docker-compose up -d

Verify HTTPS Configuration
Access https://unni.live in a web browser.


By following these steps, you'll have Nginx running with HTTPS using Let's Encrypt SSL certificates. Ensure to replace placeholders like `your-email@example.com` with your actual information.
