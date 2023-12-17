MySQL is an open-source relational database management system.
It is commonly deployed as part of the LAMP stack (which stands for Linux, Apache, MySQL, and PHP)
and, as of this writing, is the most popular open-source database in the world.

This guide outlines how to create a new MySQL user and grant them the permissions needed to perform a variety of actions.

Creating a New User

Upon installation, MySQL creates a root user account which you can use to manage your database.
This user has full privileges over the MySQL server, meaning it has complete control over every database, table, user, and so on.
Because of this, it’s best to avoid using this account outside of administrative functions.

This step outlines how to use the root MySQL user to create a new user account and grant it privileges.

In Ubuntu systems running MySQL 5.7 (and later versions),
the root MySQL user is set to authenticate using the auth_socket plugin by default rather than with a password.
This plugin requires that the name of the operating system user that invokes the MySQL client matches
the name of the MySQL user specified in the command.
This means that you need to precede the mysql command with sudo to invoke it with the privileges of
the root Ubuntu user in order to gain access to the root MySQL user

sudo mysql
