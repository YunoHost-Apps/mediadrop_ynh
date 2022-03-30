## Use

Access the site administration by writing the following address in your browser.

https://www.domain.tld/admin

User is "*admin*" and password is "*admin*"

### Troubleshooting

If you have this error into syslog file ?

`Use 'mysqld --thread_stack=#' to specify a bigger stack.")`

This is because the thread_stack option is not high enough. This option manages the stack size for each thread.

Replace into this file /etc/mysql/my.cnf

`thread_stack = 128K`

by

`thread_stack = 156K`

You can adjust it, the mysql documentation says this.

The default of 192KB (256KB for 64-bit systems) is large enough for normal operation. If the thread stack size is too small, it limits the complexity of the SQL statements that the server can handle, the recursion depth of stored procedures, and other memory-consuming actions.

Source: [Documentation MySQL](https://dev.mysql.com/doc/refman/5.7/en/server-system-variables.html#sysvar_thread_stack)
