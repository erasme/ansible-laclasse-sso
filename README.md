laclasse-sso Ansible playbook
=============================

[![Travis
CI](http://img.shields.io/travis/erasme/ansible-laclasse-sso.svg?style=flat)](http://travis-ci.org/erasme/ansible-laclasse-sso)
[![test-suite](http://img.shields.io/badge/ansible--roles--specs-ansible--laclasse--sso-blue.svg?style=flat)](https://github.com/erasme/ansible-roles-specs/tree/master/ansible-laclasse-sso/)
[![Ansible
Galaxy](http://img.shields.io/badge/galaxy-erasme.laclasse--sso-660198.svg?style=flat)](https://galaxy.ansible.com/list#/roles/3040)

This playbook will install laclasse-sso.

Requirements
------------

Role Variables
--------------

  - `simplesaml_version`: version to deploy (default: 1.9.0)
  - `simplesaml_install_directory`: where to deploy the code (default: /opt/simplesaml/)

Not used ATM:

  - `simplesaml_base_url`: base path for URI (default: '/saml/')
  - `simplesaml_auth_adminpassword`: admin password (default: 'password')
  - `simplesaml_secretsalt`: secret SALT (default: 'pepper')
  - `simplesaml_logfile`: log file path (default: '/tmp/simplesamlphp.log')
  - `simplesaml_cookiename`: HTTP cookie name to use (default: 'saml')
  - `simplesaml_language`: interface language (default: 'en')
  - `simplesaml_port`: HTTP port to use (default: 1234)

laclasse_slack:
  host: localhost
  token: none
  channel: none


  - `laclasse_admin_email`: some@admin.org
  - `laclasse_annuaire_sso_api_url`: '/api/sso'
  - `laclasse_cookie_domain`: laclasse.com
  - `laclasse_redis.server`: 'redisserver'
  - `laclasse_redis.port`: 6379
  - `laclasse_sso_baseurl`: '/sso'
  - `laclasse_sso_cas_allowed`: [ '*://*some.server.url*' ]
  - `laclasse_sso_deploy_user`: someuser
  - `laclasse_sso_display_news`: true
  - `#` Running mode :
  - `#` 'dev'   : http protocol allowed
  - `#` 'prod'  : https required
  - `#` 'debug' : 'dev' mode plus debug info display
  - `laclasse_sso_mode`: 'dev'
  - `#` Debug level & file
  - `laclasse_sso_log_file`: /tmp/log-sso.txt
  - `laclasse_sso_log_level`: 5
  - `laclasse_sso_path`: '/'
  - `laclasse_sso_port`: 9292
  - `laclasse_sso_redis_root`: 'someredispath'
  - `laclasse_sso_redis_news_root`: 'someredispath'
  - `laclasse_sso_repos`: https://github.com/laclasse-com/php-cas-server.git
  - `laclasse_sso_twitter`:
  - `laclasse_sso_twitter.account`: '@someaccount'
  - `laclasse_sso_twitter.hashtag`: '#somehashtag'
  - `laclasse_sso_twitter.consumer_key`: 'consumerkey'
  - `laclasse_sso_twitter.consumer_secret`: 'consumersecret'
  - `laclasse_sso_twitter.oauth_token`: 'oauthtoken'
  - `laclasse_sso_twitter.oauth_secret`: 'oauthsecret'
  - `laclasse_sso_version`: '3.3.14'


Tags
----

  - `simplesaml`,`saml`: applies to the whole role

Dependencies
------------

  - erasme.simplesaml

Example Playbook
----------------

This is mainly used as a dependency in your existing playbooks, like:

    dependencies:
      - { role: erasme.simplesaml }

but can be used in playbooks also :

    - name: saml server
      hosts: ssoservers
      roles:
        - erasme.simplesaml

License
-------

MIT

Author Information
------------------

Created for @erasme by @leucos.

