## Document for restore-backup for disaster recovery 

### First take the full-backup of client for restore
### To create  the backup run the command
```bash
run                  # It shows all the cleint

(select cleint)      # Choose the cleint according the number
                     # It shows 3 optins yes/mod/no
mod                  # For incremental backup 
1                   # choes level one
2                   # after this choose 2 for incremental
yes                # Choose the yes parameter for full backup otherwise mod for modify the backup
 
                  # It take some time for took full-backup
```

## After completing the full backup take the restore-backup
```bash
restore             # It shows all the default parameter for restore
5                   # Choose the 5-one,it is for recent full-backup

                     # After this it shows all the recent full-backup client
(Selcet client)      # Choose the client according then number for restore

mark *               # It select all the files from client

done          

                    # After done, it shows again all client for restore-backup client
(Choose client)     # We choose different client for restore the client for disaster recovery
mod                # After this select mod option 
where              # In this, define the path for restore-client
mod                # Again choose mod for restore-client
5                  # Choose the number 5 parameter restore -client
yes                # It start the restore 
st dir             # check the restore status 
                   # it takes few minutes for completing the restore 
                     
```


 
