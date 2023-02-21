# Docker Docs

# Docker Run port
`docker run -d -p <Host port>:<Container Port>`

i.e. Use Host IP to `127.0.0.1:10101`, but Container **Docker 101 tutorial** default Nginx port is **80**, use `-p 10101:80` is solve.

If need modify nginx port, update `/etc/nginx/conf.d/default.conf`file.
