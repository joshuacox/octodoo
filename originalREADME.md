Run OpenERP on Debian - September 2014
--------------------------------------

*Built with Docker 1.2.0*

Features:

 - Debian Jessie
 - PostgreSQL 9.3 or 9.4
 - OpenERP 7.0 or 8.0
 - SSH server
 - Supervisor

(Ubuntu build : [tinyerp/ubuntu-openerp][1])

Usage:

 - Install Docker: [docs.docker.com][2]
 - Execute
 `docker run -d --name openerp -p 8069:8069 tinyerp/debian-openerp`
 - Browse [http://&lt;your server ip address&gt;:8069/][3]
 - Stop and start again
   - `docker stop openerp`
   - `docker start openerp`

Manhole access:

 1. `OPENERP_IP=$(docker inspect --format='{{.NetworkSettings.IPAddress}}' openerp)`
 2. `ssh-keygen -R $OPENERP_IP` (because Docker assigns the same IP to different hosts)
 3. `ssh root@$OPENERP_IP -p 22` (default password `password`)

Images available:

 - `tinyerp/debian-openerp:6.1`
 - `tinyerp/debian-openerp:7.0` (same as) `tinyerp/debian-openerp`
 - `tinyerp/debian-openerp:8.0` (same as) `tinyerp/debian-odoo`

Source repository: [https://github.com/tinyerp/odoo-docker][4]

  [1]: https://registry.hub.docker.com/u/tinyerp/ubuntu-openerp/
  [2]: https://docs.docker.com/ "docs.docker.com"
  [3]: http://127.0.0.1:8069/
  [4]: https://github.com/tinyerp/odoo-docker
