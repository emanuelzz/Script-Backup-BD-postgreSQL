# Script-Backup-BD-postgreSQL

#!/bin/bash

DATA='/bin/date+%Y-%m-%d'

su -postgres 

export PGPASSWORD = "senha do postgres" 

 
pg_dump -U usuario_postgres -h local_banco_de_dados -O -o -b -F c nome_banco_dados > nome_do_backup.backup


pg_restore -U usuario_postgres -h local_banco_de_dados -d nome_banco_dados > nome_do_backup.backup


Createdb -T template0 restored_database


Psql restore_database <database.bak


Psql --set ON_ERROR_STOP = em restore_database < backup_file


