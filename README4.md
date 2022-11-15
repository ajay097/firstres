## Document for restore-backup for disaster recovery ------

### First took the full-backup of cleint for restore---
### To create  the backup run the command----
```bash
run           # It shows all the cleint

16           # Choose the cleint according the number
             # It shows 3 optins yes/mod/no
yes          # Choose the yes parameter for full backup otherwise mod for modify the backup
 
St dir       # Check the cleint status 
             # It take some time for took full-backup
```

## After completing the full backup took the restore-backup----
```bash
restore       # It shows all the default parameter for restore
5             # Choose the 5-one,it is for recent full-backup

              # After this it shows all the recent full-backup client
16            # Choose the cleint according then number for restore

mark *        # It select all the files from cleint

done          

             # After done, it shows again all cleint for restore-backup cleint
18           # We choose different cleint for restore the client for disaster recovery
mod          # After this select mod option 
where        # in this define the path for restore-cleint
yes          # It start the restore 
st dir       # check the restore status 
             # it takes few minutes for completing the restore 
                     
```


 
