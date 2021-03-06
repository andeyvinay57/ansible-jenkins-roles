****************************
ANSIBLE JENKINS DEVOPS ROLES
****************************
.. contents:: Table of Contents

A set of roles to support automated installation of `jenkins`_ with `ansible`_.

This is not a one size fits all role. Extensive customisation should be expected before your jenkins is running but
at that point its running **FULLY** configured. No manual intervention needed. At least that is the goal.

For an example playbook that makes use of this roles check my `examples repo`_.

FEATURES
--------
There are several steps already implemented

#. Download `apache tomcat`_ and setup a tomcat instance
#. Download jenkins and drop it into tomcat
#. Download a configured set of plugins and activate them.
#. Configure jenkins

   * authorization strategy
   * authentication strategy
   * notification settings
   * location properties
   * users (for hudson_private authentication strategy aka "Jenkins' own user database")
   * permissions (for hudson authorization strategies project_matrix and global_matrix)

#. Create a bootstrap job that checks out from vcs and executes all `bootstrap/*.job` scripts with the `job-dsl plugin`_.

.. IMPORTANT::
   All roles are designed to be used outside this playbook.

DOCUMENTATION
-------------
Documentation is done with sphinx. The repository contains a alpha version of a ansible sphinx-domain in the
subfolder `doc/ansible`. The documentation itself is hosted at `Read The Docs`_

OUTLOOK
-------
There are several action points left on my plate. Those i remember right now :)

Write a ansible coding standard::
  The idea is to document all rules and conventions applied when writing these roles. I have for example a strict *no
  become for roles* policy.
Implement more configuration roles::
  Jenkins configuration is complex. I will implement all configuration i need for my daily work.
Provide job templates::
  The idea is to provide a list of job templates for common jobs. Eg build a

  - ruby gem
  - python egg
  - ...

Finish the sphinx-ansible domain::
  And then bring it up to sphinx-contrib.

AUTHOR
------
`Michael Jansen`_ created Ansible Jenkins DevOps Roles

LICENSE
-------
Please see `LICENSE <https://github.com/jansenm/ansible-jenkins-roles/blob/master/LICENSE>`_

.. Github does not support includes in README files!!!!!!
.. _Michael Jansen: http://michael-jansen.biz
.. _Read The Docs: http://ansible-jenkins-roles.readthedocs.org/en/latest/
.. _ansible: http://ansible.com
.. _apache tomcat: https://tomcat.apache.org/
.. _examples repo: https://github.com/jansenm/ansible-jenkins-roles-example
.. _jenkins: http://jenkins-ci.org
.. _job-dsl plugin: https://github.com/jenkinsci/job-dsl-plugin
