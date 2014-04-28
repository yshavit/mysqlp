Helper prompt for MySQL's `--login-path`
---

MySQL has a neat option, `--login-path` (versions 5.6.6+). You can set up login info (host, username, password) using [mysql_login_path][1], and MySQL will remember those credentials for you. The problem (for me) is that I forget what `login-path` labels I've created! This script simply lists the defined paths for you, then lets you select which you want to use.

`mysqlp` doesn't take any arguments, but any arguments you pass will be forwarded to the `mysql` client. For instance:

    $ mysqlp -A my_schema_to_connect_to
    0: first-login
    1: another-login
    2: yet-another-login
    Connect to which profile? 1

Would launch `mysql --login-path another-login -A my_schema_to_connect_to`

That's it.

[1]: https://dev.mysql.com/doc/refman/5.6/en/mysql-config-editor.html
