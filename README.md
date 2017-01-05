# django-caddy

[![dockeri.co](http://dockeri.co/image/lgatica/django-caddy)](https://hub.docker.com/r/lgatica/django-caddy/)

> Docker Image for reverse proxy django apps with caddyserver and alpine linux

Supported tags and respective Dockerfile links

- 0.9.4, latest ([0.9.4/Dockerfile](https://github.com/lgaticaq/django-caddy/blob/master/0.9.4/Dockerfile))
- 0.9.3 ([0.9.3/Dockerfile](https://github.com/lgaticaq/django-caddy/blob/master/0.9.3/Dockerfile))

## Instructions

```bash
docker create volume --name static
docker create volume --name media
docker create volume --name logs
docker run -d --name django -v static:/path/to/static -v media:/path/to/media -e PORT 8000 your-django-image-with-gunicorn
docker run -d --name caddy --link django:django -v static:/var/www/static -v media:/var/www/media -v logs:/var/log -e PORT 8000 lgatica/django-caddy
```
