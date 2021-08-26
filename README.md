# Domains

You can run multiple virtual hosts for mail/webmail using one set of services. 
First, login to `<domain>/?admin` with admin/12345 and change password. Then 
go to `Domains`, remove existing domains and add `<domain>` as:
* name: `<domain>`

#### IMAP
* server: mail
* secure: SSL/TLS
* port: 993

#### SMTP
* server: mail
* secure: STARTTLS
* port: 587

#### SIEVE
* allow sieve scripts: yes
* server: mail
* secure: STARTTLS
* port: 4190

# Authentication
From `Packages` on the left install `Change password (LDAP)` then go to plugins and enable `ldap-change-password`. Click on the plugin and enter the following:
* hostname: ldaps://ldap.\<domain>
* port: 636
* user DN format: uid={email:user},ou={email:domain},dc=account,dc=ldap
* password field: userPassword
* encryption type: SHA
* alloed emails: *
