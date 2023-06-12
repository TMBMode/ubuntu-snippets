## Reverse Proxy
- When binding a domain, we stop using the `http://ip:port/` way of things
- Instead, we reverse proxy the port to a certain subdomain, and we end up with `http://sub.domain.tld/`
---
Ensure the subdomains are configured with the DNS provider
```shell
sudo apt install nginx
sudo nano /etc/nginx/conf.d/<name>.conf
```
Where `<name>` is the name of the configuration file (I highly suggest using the subdomain name to avoid confusion, e.g. `service1` when the URL is `service1.mysite.com`)

Paste the following to the file:
```
server {
    listen 80;
    server_name <sub.domain.tld>;

    location / {
        proxy_pass http://127.0.0.1:<port>;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```
Remember to replace the `server_name` attribute with your domain name (if you do not want to use a subdomain, then just use the format `domain.tld`). Also, substitute in the port of your project for `<port>`. Do not include `<>` in the actual config file.

```shell
sudo nginx -t
```
If the command reports no errors, we're good to go!
```shell
sudo service nginx restart
```
And things should be working