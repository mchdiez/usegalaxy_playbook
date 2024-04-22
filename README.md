Welcome to UseGalaxy.es, the official INB's galaxy server

Notes about the configuration of this specific ansible galaxy playbook:

1. Galaxy default's SSL configuration is not included, as we use our own SSL certificates. Hence, the configuration of certbot at /group_vars/galaxyservers has been skipped and the file /templates/nginx/galaxy.j2 showcases the line:
        - listen        *:80 default_server;
instead of:
        - listen        *:443 ssl default_server;
