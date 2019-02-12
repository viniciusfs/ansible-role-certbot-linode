Certbot Linode
==============

Use Certbot and Linode DNS plugin to create Let's Encrypt root and wildcard certificates.

Requirements
------------

- [Linode DNS setup](https://www.linode.com/docs/networking/dns/common-dns-configurations/#use-wildcard-dns-records)
- [Linode API Key](https://www.linode.com/docs/platform/api/getting-started-with-the-linode-api/#create-an-api-token)

Role Variables
--------------

    certbot_email: "linode@example.com"

Your email address

    certbot_linode_api_key: ''

Your Linode API Key

    certbot_domains:
      - domain: example.com
      - domain: other.net

Domains list to create the certificates for.

Example Playbook
----------------

    - hosts: servers
      vars:
        certbot_email: "admin@example.com"
        certbot_linode_api_key: 'myapikey'
        certbot_domains:
          - domain: "example.com"
          - domain: "other.net"
            email: "admin@other.net"

      roles:
         - viniciusfs.certbot-linode

Troubleshooting
---------------

Certbot DNS plugin waits 20 minutes for DNS replication, set your Ansible
[timeout configuration](https://docs.ansible.com/ansible/latest/reference_appendices/config.html#default-timeout)
for appropriate value.

License
-------

MIT

Author Information
------------------

Created by [Vinicius Figueiredo](https://www.ultrav.com.br).
