# Supported tags and respective Dockerfile links

- [`0.8.1` (*0.8.1/Dockerfile*)](https://github.com/Accenture/certbot/blob/master/Dockerfile)

# What is Certbot?

Certbot is a fully-featured, extensible client for the Let's
Encrypt CA (or any other CA that speaks the [ACME](https://github.com/ietf-wg-acme/acme/blob/master/draft-ietf-acme-acme.md)
protocol) that can automate the tasks of obtaining certificates and
configuring webservers to use them. This client runs on Unix-based operating
systems.

Until May 2016, Certbot was named simply ``letsencrypt`` or ``letsencrypt-auto``,
depending on install method. Instructions on the Internet, and some pieces of the
software, may still refer to this older name.

# How to use this image

The easiest way how to run Certbot image is as follow:
```
$ docker run --rm -it \
    -p 80:80 -p 443:443 \
    -v <store-path>:/etc/letsencrypt
    --net=<your-network-name> \
    adop/certbot:VERSION <command>
```
Where ```command``` is ```certbot``` command.

Example:
```
certbot certonly --standalone -d ${DOMAIN_NAME} --text --register-unsafely-without-email --agree-tos"
```

after the above, the Certbot will request SSL certificates for the ```$DOMAIN_NAME``` and save it to ```<store-path>```.

# License
Please view [licence information](LICENCE.md) for the software contained on this image.

# Supported Docker versions

This image is officially supported on Docker version 1.11.1.

# User feedback

## Documentation
Documentation for this image is available in the [letsencrypt](https://letsencrypt.org).
Additional documentaion can be found under the [`docker-library/docs` GitHub repo](https://github.com/docker-library/docs). Be sure to familiarize yourself with the [repository's `README.md` file](https://github.com/docker-library/docs/blob/master/README.md) before attempting a pull request.

## Issues
If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/Accenture/letsencrypt/issues).

## Contribute
You are invited to contribute new features, fixes, or updates, large or small; we are always thrilled to receive pull requests, and do our best to process them as fast as we can.

Before you start to code, we recommend discussing your plans through a [GitHub issue](https://github.com/Accenture/letsencrypt/issues), especially for more ambitious contributions. This gives other contributors a chance to point you in the right direction, give you feedback on your design, and help you find out if someone else is working on the same thing.
