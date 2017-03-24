Koha-Dashboards
=========

Add a set of named pipes for your Koha instances that output useful information

Requirements
------------

This role works for the Debian package version of Koha

Role Variables
--------------

Define in number of pipes to be created in under the 'queries' variable, which is a list of hashes. Each element in the queries list should have a name and sql key, the description is for humans only and is not used by Ansible for anything.

queries:
    - name: bibcount
      description: Outputs the number of marc records in the database
      sql: "SELECT COUNT(*) FROM biblio"

    - name: patroncount
      description: Outputs the number of patrons in the database
      sql: "SELECT COUNT(*) FROM borrowers"

Dependencies
------------

This role has no dependencies on other Ansible roles

Example Playbook
----------------

- hosts: all
  roles:
     - koha-dashboard

License
-------

CC-BY

Author Information
------------------

Kyle M Hall, ByWater Solutions
http://kylehall.info
http://bywatersolutions.com
