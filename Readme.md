# Project: Building a Web Server

## Description
This project, developed by Yogi Fitriadi Rakhim, fulfills the "Belajar Jaringan Komputer untuk Pemula" course on Dicoding for IDCamp 2023. The project involves setting up a web server, configuring NGINX as a reverse proxy server, implementing rate limiting, and making additional changes to the NGINX configuration.

## Project Tasks

### Task 1: Setting up the Web Server
The initial step in building a web server involves the following preparations:

1. Clone the GitHub repository provided by Dicoding [GitHub Repository](https://github.com/dicodingacademy/a387-jarkom-labs.git).
2. Install NGINX.
3. Ensure that both the Node.js web server and NGINX are accessible and functioning correctly.

### Task 2: Configuring NGINX as a Reverse Proxy Server
After successfully completing Task 1, proceed to configure NGINX, which has already been installed, as a reverse proxy server. This configuration allows requests to be forwarded to the web server when accessed through port 80, which is used by NGINX.

### Task 3: Implementing Limit Access in NGINX
Following the completion of Task 2, continue working on your project by fulfilling Task 3. This task requires you to configure NGINX (reverse proxy server) to implement rate limiting, enhancing the security of the web server.

### Additional Tasks for NGINX
In addition to the main tasks, the following changes need to be made to the NGINX configuration:

1. Change the NGINX port from 80 to 3000 (not the Node.js web server's port).
   ```nginx
   server {
       listen 3000;
       ...
   }

2. Modify the rate limit configuration to allow 6 requests per minute, which is equivalent to 1 request every 10 seconds.
   ```nginx
   limit_req_zone $binary_remote_addr zone=one:10m rate=6r/m;
    ...
    location / {
    root html;
    index index.html index.htm;
    proxy_pass http://localhost:8000/;
    limit_req zone=one;
    }
3. Change the response from the Node.js web server, which initially displayed "Hello world!", to my full name, "Yogi Fitriadi Rakhim".
---
## Special Thanks

I would like to express my heartfelt gratitude to Dicoding and IDCamp 2023 for providing this incredible learning opportunity and project. This experience has been instrumental in enhancing my knowledge of networking, web server configurations, and NGINX, and has helped me develop valuable skills in the field of computer networking.

I am truly thankful for the chance to be a part of IDCamp 2023, and I look forward to applying the skills and knowledge I've acquired
