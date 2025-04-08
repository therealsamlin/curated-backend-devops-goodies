# Enable Audit Logs for CloudSQL MySQL

Turn on cloudsql_mysql_audit flag (terraform), this will trigger a database instance reboot.

```
database_flags { name = "cloudsql_mysql_audit" value = "ON" }
```

Insert audit rules in MySQL, run the reload command to have them take effect

```
-- Create Audit rules for all users on database production_db
CALL mysql.cloudsql_create_audit_rule('*@*','production_db','*','*','B',1,@outval,@outmsg);

-- Audit all DDL operations across all databases
CALL mysql.cloudsql_create_audit_rule('*','*','*','ddl','B',1,@outval,@outmsg);

-- Audit all security commands across all databases
CALL mysql.cloudsql_create_audit_rule('*','*','*','grant','B',1,@outval,@outmsg);
CALL mysql.cloudsql_create_audit_rule('*','*','*','revoke','B',1,@outval,@outmsg);

-- Audit DML only on sensitive tables
CALL mysql.cloudsql_create_audit_rule('*','production_db','customer_data','dml','B',1,@outval,@outmsg);
CALL mysql.cloudsql_create_audit_rule('*','production_db','financial_data','dml','B',1,@outval,@outmsg);

-- Exclude high-volume service accounts
CALL mysql.cloudsql_create_audit_rule('user*@*','*','*','*','E',1, @outval,@outmsg);

-- Exclude routine maintenance query
CALL mysql.cloudsql_create_audit_rule('`root`@`127.0.0.1`','mysql','heartbeat','insert','E',1,@outval,@outmsg);

-- Exclude prober
CALL mysql.cloudsql_create_audit_rule('__google_connectivity_prober*@*','*','*','*','E',1, @outval,@outmsg);

-- Exclude connect & disconnect from root
CALL mysql.cloudsql_create_audit_rule('root','*','*','connect','E',1,@outval,@outmsg);
CALL mysql.cloudsql_create_audit_rule('root','*','*','disconnect','E',1,@outval,@outmsg);

-- Reload audit rule so it'll take effect
CALL mysql.cloudsql_reload_audit_rule(1);

-- List audit rules
CALL mysql.cloudsql_list_audit_rule('*',@outval,@outmsg);
SELECT @outval, @outmsg;

-- Delete audit rules
CALL mysql.cloudsql_delete_audit_rule('1,2',0,@outval,@outmsg);
SELECT @outval, @outmsg;
```
