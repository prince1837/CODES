export collections from mongo DB into json file

        mongoexport -d "database_name" -c "collections_name" -o "json_file_name"
    
Import collection from json file into mongo DB

        mongoimport -d "database_name" -c "collections_name" "json_file_name"
        
export database In Local Directory

        mongodump --host=IP_host --port=27017 -d databaseName --username=database_username --password="database_password" --out=file_name of Dump

import database from  Local Directory into database

        mongoresore database_dir_name
      
