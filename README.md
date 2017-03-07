Ansible-Role: ODBC
=========

Install ODBC on RedHat or CentOS and manage system wide database connections.

Requirements
------------

None.

Role Variables
--------------

    # Define ODBC-packages
    odbc_packages:
      - unixODBC
      - unixODBC-devel
      - freetds
      - freetds-devel

    # Path to odbc configuration
    odbc_file: /etc/odbc.ini
    
    # Custom odbc entries to be added
    odbc_connections:
      - name: MyConnection
        driver: FreeTDS
        description: This is a test connection
        server: example.com
        port: 1433
        tds_version: "8.0"
        database: MY_DATABASE
      - name: MyConnection2
        driver: FreeTDS
        description: This is a second test connection
        server: example.com
        port: 1433
        tds_version: "8.0"
        database: MY_DATABASE_2
        characterset: UTF-8

    # Custom odbc file snippets to be added
    odbc_file_snippets:
      - /opt/my_snippet_which_will_be_included_in_config.ini

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: sguter90.odbc }

License
-------

BSD

Author Information
------------------

This role was created in 2015 by [Christoph Mueller](http://flying-lama.com/).
