Requirements
============
- docker
- docker-compose
- git

Install
=======
```bash
# create network
docker network create nginx-proxy
# clone project
git clone https://github.com/maxoralbay/reverse-proxy
cd reverse-proxy
docker-compose up -d
```

Usage
=====
```bash
# create new project
create simple web server with reverse-proxy network
sudo nano ## '0.0.0.0 example.com' >> /etc/hosts
docker run webserver --name webserver --network reverse-proxy --env VIRTUAL_HOST=example.com
# renew certificates
docker-compose run --rm certbot renew
# remove project
docker-compose down
```

Todos
=====
- [ ] Add support for multiple domains
- [ ] Check if the certificate is valid (Let's Encrypt)) 