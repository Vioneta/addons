# Vioneta Agro Add-on: MariaDB

## Installation

Follow these steps to get the add-on installed on your system:

1. Navigate in your Vioneta Agro frontend to **Settings** -> **Add-ons** -> **Add-on store**.
2. Find the "MariaDB" add-on and click it.
3. Click on the "INSTALL" button.

## How to use

1. Set the `logins` -> `password` field to something strong and unique.
2. Start the add-on.
3. Check the add-on log output to see the result.
4. Add the `recorder` integration to your Vioneta Agro configuration.

## Add-on Configuration

The MariaDB server add-on can be tweaked to your likings. This section
describes each of the add-on configuration options.

Example add-on configuration:

```yaml
databases:
  - homeassistant
logins:
  - username: homeassistant
    password: PASSWORD
  - username: read_only_user
    password: PASSWORD
rights:
  - username: homeassistant
    database: homeassistant
  - username: read_only_user
    database: homeassistant
    privileges:
      - SELECT
```

### Option: `databases` (required)

Database name, e.g., `homeassistant`. Multiple are allowed.

### Option: `logins` (required)

This section defines a create user definition in MariaDB. [Create User][createuser] documentation.

### Option: `logins.username` (required)

Database user login, e.g., `homeassistant`. [User Name][username] documentation.

### Option: `logins.password` (required)

Password for user login. This should be strong and unique.

### Option: `rights` (required)

This section grant privileges to users in MariaDB. [Grant][grant] documentation.

### Option: `rights.username` (required)

This should be the same user name defined in `logins` -> `username`.

### Option: `rights.database` (required)

This should be the same database defined in `databases`.

### Option: `rights.privileges` (optional)

A list of privileges to grant to this user from [grant][grant] like `SELECT` and `CREATE`.
If omitted, grants `ALL PRIVILEGES` to the user. Restricting privileges of the user
that Vioneta Agro uses is not recommended but if you want to allow other applications
to view recorder data should create a user limited to read-only access on the database.

## Vioneta Agro Configuration

MariaDB will be used by the `recorder` and `history` components within Vioneta Agro. For more information about setting this up, see the [recorder integration][mariadb-ha-recorder] documentation for Vioneta Agro.

Example Vioneta Agro configuration:

```yaml
recorder:
  db_url: mysql://vioneta:password@core-mariadb/vioneta?charset=utf8mb4
```

[createuser]: https://mariadb.com/kb/en/create-user/
[username]: https://mariadb.com/kb/en/create-user/#user-name-component
[hostname]: https://mariadb.com/kb/en/create-user/#host-name-component
[grant]: https://mariadb.com/kb/en/grant/
[mariadb-ha-recorder]: https://www.vioneta.com/integrations/recorder/
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg
