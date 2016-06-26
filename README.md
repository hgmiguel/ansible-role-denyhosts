# ansible-role-denyhosts

[![Build Status](https://travis-ci.org/tkimball83/ansible-role-denyhosts.svg?branch=master)](https://travis-ci.org/tkimball83/ansible-role-denyhosts)

This role installs and enables DenyHosts on RHEL/CentOS.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    denyhosts_admin_email: ''
    denyhosts_age_reset_invalid: 10d
    denyhosts_age_reset_restricted: 25d
    denyhosts_age_reset_root: 25d
    denyhosts_age_reset_valid: 5d
    denyhosts_allowed_hosts_hostname_lookup: False
    denyhosts_block_service: sshd
    denyhosts_daemon_log: /var/log/denyhosts
    denyhosts_daemon_purge: 1h
    denyhosts_daemon_sleep: 30s
    denyhosts_deny_threshold_invalid: 5
    denyhosts_deny_threshold_restricted: 1
    denyhosts_deny_threshold_root: 1
    denyhosts_deny_threshold_valid: 10
    denyhosts_etc_dir: /etc
    denyhosts_hostname_lookup: False
    denyhosts_hosts_deny: /etc/hosts.deny
    denyhosts_lock_file: /var/lock/subsys/denyhosts
    denyhosts_purge_deny: 4w 
    denyhosts_secure_log: /var/log/secure
    denyhosts_smtp_from: 'DenyHosts <nobody@localhost>'
    denyhosts_smtp_host: localhost
    denyhosts_smtp_port: 25
    denyhosts_smtp_subject: 'DenyHosts Report from $[HOSTNAME]'
    denyhosts_suspicious_login_report_allowed_hosts: True
    denyhosts_sync_download: False
    denyhosts_sync_upload: False
    denyhosts_work_dir: /var/lib/denyhosts
    denyhosts_allowed_hosts: []

## Dependencies

 * https://galaxy.ansible.com/tkimball83/epel/
 
## Example Playbook

    - hosts: servers
      roles:
        - role: tkimball83.denyhosts
          denyhosts_admin_email: your@email.com
          denyhosts_allowed_hosts:
            - 127.0.0.1

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
