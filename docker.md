# Docker Docs

# Docker Run port
`docker run -d -p <Host port>:<Container Port>`

i.e. Use Host IP of `127.0.0.1:10101`, but Container **Docker 101 tutorial** default Nginx port is **80**, use `-p 10101:80` is solve.

If need modify nginx port, update `/etc/nginx/conf.d/default.conf`file.

- `-d` - run the container in detached mode (in the background)
- `-p 11110:80` - map port 11110 of the host to port 80 in the container
