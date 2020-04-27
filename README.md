**docker-compose.yaml**

DB_ROOT_PASSWORD and MYSQL_ROOT_PASSWORD: Root's password of MariaDB.

MASTER_PASSWORD: Admin's password.
- Ps: The variables DB_ROOT_PASSWORD and MYSQL_ROOT_PASSWORD must be same value.

LIBRARY_NAME: Library's name for installation.

SLEEP: MariaDB connection timeout.

INTRAPORT: Port for administrator painel.

DB_HOST: MariaDB's container name (defined in container_name).

- Ps: The INTRAPORT value must be expotred in ports.
 - Example INTRAPORT: 5555
   - ports:
     - 5555:5555

Administrator user: koha_<LIBRARY_NAME>, **default: koha_koha**.

Password: <MASTER_PASSWORD>, **default: koha123**.
