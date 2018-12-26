sa-mysql-galera
========

[![Build Status](https://travis-ci.org/softasap/sa-mysql-galera.svg?branch=master)](https://travis-ci.org/softasap/sa-mysql-galera)

classic mysql install from apt

Example of usage (all parameters are optional)

Simple

```YAML
  roles:
    - {
        role: "sa-mysql-galera"
      }
```

Advanced:

```YAML
  roles:
    - {
        role: "sa-mysql-galera",
        option_harden_mysql: true,  
        mysql_root_user: root,
        mysql_root_password: devroot,
      - mysql_databases:
        - name: app_db
          encoding: utf8
          collation: utf8_general_ci
      - mysql_users:
        - name: app_user
          host: "%"
          password: dYud8LHBBptGN96LSn0e
          priv: "app_db.*:ALL"
      }
```

Note: if you ever needed to downgrade mysql on xenial to 5.6 rather than default 5.7 available now - use this replacement role `sa-mysql-galera56`:

https://github.com/softasap/sa-mysql-galera56


Usage with ansible galaxy workflow
----------------------------------

If you installed the sa-mysql-galera role using the command


`
   ansible-galaxy install softasap.sa-mysql-galera
`

the role will be available in the folder library/softasap.sa-mysql-galera
Please adjust the path accordingly.

```YAML

     - {
         role: "softasap.sa-mysql-galera"
       }

```

requirements.yml snippet: 

```YAML
- src: softasap.sa-mysql-galera
  name: sa-mysql-galera
```




Copyright and license
---------------------

Code is dual licensed under the [BSD 3 clause] (https://opensource.org/licenses/BSD-3-Clause) and the [MIT License] (http://opensource.org/licenses/MIT). Choose the one that suits you best.

Reach us:

Subscribe for roles updates at [FB] (https://www.facebook.com/SoftAsap/)

Join gitter discussion channel at [Gitter](https://gitter.im/softasap)

Discover other roles at  http://www.softasap.com/roles/registry_generated.html

visit our blog at http://www.softasap.com/blog/archive.html


