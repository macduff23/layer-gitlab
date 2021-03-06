# Overview

This charm provides the GitLab open source git repository management platform. 

GitLab includes git repository management, code reviews, issue tracking, wikis and much more. 
GitLab comes with GitLab CI, an easy to use continuous integration and deployment tool.

Discuss issues and plan milestones. Do code reviews and make line comments. Mention your colleagues anywhere. View activity streams of projects or people.

GitLab has integrations for tons of tools such as Slack, Hipchat, LDAP, JIRA, Jenkins, many types of hooks and a complete API.

# Usage

To deploy Gitlab simply run:

    juju deploy cs:~spiculecharms/gitlab-server
    juju expose gitlab-server

Login to the new server with the username: root and a password of your choice and on first login you will be instructed 
to change the root password.

To use it with an HTTP endpoint like HA Proxy you need to run

    juju deploy haproxy
    juju add-relation haproxy gitlab

This charm also supports the SSL Termination Proxy charm to provide SSL encryption.

Once deployed you should change the external_url from localhost to the FQDN of your Gitlab client. Whilst it doesn't affect the operation of the server, it does ensure links and urls generated by Gitlab are correct for remote operation.

    juju config gitlab-server external_url=<your fqdn>
 
# Limitations

Curently there is no HA mode or scale out.

# Code

Source Code: https://github.com/osbi/layer-gitlab

# Contact Information

- <tom@spicule.co.uk>
