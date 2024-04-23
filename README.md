Welcome to UseGalaxy.es, the official INB's galaxy server

Notes about the configuration of this specific ansible galaxy playbook:

1. Galaxy default's SSL configuration is not included, as we use our own SSL certificates. Hence, the configuration of certbot at /group_vars/galaxyservers has been skipped and the file /templates/nginx/galaxy.j2 showcases the line:
        - listen        *:80 default_server;
instead of:
        - listen        *:443 ssl default_server;

2. For TUSD module installation, the package "ansible'core" had to be installed separately from ansible as a whole using pip (following these instructions: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html). Not doing so led to legacy version issues with unpack module.
