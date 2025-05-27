# Caddy Public Hosting

This project allows you to publish your local projects to the internet using your public IP and a custom domain, leveraging the power of Caddy as a web server and reverse proxy.

## Step 1: Get Your Public IP

To easily obtain your public IP address, you can use the included script:

```
npm run get-ip
```

This will execute the `get-public-ip.bat` file, which uses curl to fetch your public IP from myip.directadmin.com. Useful for DNS configuration and troubleshooting.

## Step 2: DNS Configuration

In your Hosting Panel, go to **DNS Management** and add a subdomain with an "A" record pointing to your public IP address.
![image](https://github.com/user-attachments/assets/97acc341-8a19-4921-b578-e535e6e16718)

## Step 3: Router Port Forwarding

Access your router and configure **Port Forwarding**:
- Forward WAN port 80 to your destination PC on port 80.
- Forward WAN port 443 to your destination PC on port 443.

This ensures HTTP and HTTPS traffic reaches your server.

## Step 4: Caddyfile Configuration

Edit the `Caddyfile` to add your domain and configure how requests are handled. For example:

```
your-subdomain.yourdomain.com {
    reverse_proxy localhost:3000
}
```

You can add multiple sites or services by repeating the block with different domains or ports.

## Step 5: Run the Service

Start the Caddy server by running:

```
caddy.exe run
```

Caddy will automatically obtain SSL certificates and serve your projects securely.

---

## Copyright & Official URL

Official project URL: [https://github.com/MarAntBQ/Caddy](https://github.com/MarAntBQ/Caddy)

These instructions were created by Marco Antonio Bustillos ([https://github.com/MarAntBQ/](https://github.com/MarAntBQ/))

The purpose of this guide is to help you serve projects using a public IP, making it easy for the community to contribute and improve. The goal is to have a ready-to-use, hassle-free solution for quick deployment.

You can always download the latest version of the executable file (.exe) from the official Caddy website: [https://caddyserver.com/download](https://caddyserver.com/download)

Caddy is an open-source project. For more details, visit the official repository: [https://github.com/caddyserver/caddy](https://github.com/caddyserver/caddy)
