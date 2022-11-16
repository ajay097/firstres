
This is manually for restore

## Manually Restore a client by bacula-backup 

### First take the full backup of client for restore

### After this start the restore of client
```bash
restore
```

### It shows all the default parameter for restore
### Choose the 5-one,it is for recent full-backup
```bash             
5                 
```
### After this it shows all the recent of full-backup client
### Choose the client according the number for restore                    
```bash
(Select client)      
```
### After this select all the files from client
```bash
mark *               
```
### After this do done, for continue 
```bash
done          
```
### Again it shows all client for restore-client
### We choose different client for restore the client for disaster recovery 
```bash
(Choose client) 
```  
### After this select mod option for modify the restore
```bash 
mod    
```
### In this, define the path for restore-client
```bash
where 
```
### Again choose mod for restore-client
```bash             
mod 
```  
### Choose the number 5 parameter restore -client
```bash           
5      
```    
### It start the restore
```bash        
yes 
```   
### check the restore status 
### it takes few minutes for completing the restore 
```bash          
st dir              
```             
                     


