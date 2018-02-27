## Windows
 - Download: [MongoDB](https://www.mongodb.com/download-center?jmp=nav#community) & Install msi.   
 - Go: `C:\Program Files\MongoDB\Server\{version}`
 - Create `mongod.cfg` in 'bin' folder    
 
`C:\Program Files\MongoDB\Server\{version}\bin\mongod.cfg`:
```
systemLog:
    destination: file
    path: c:\myapp\log\mongod.log
storage:
    dbPath: c:\myapp\data\db
```
Details: [Configuration File Options](https://docs.mongodb.com/manual/reference/configuration-options/)

 - Create 'myapp' folder in C drive
 - Create 'log' & 'data' folder in 'myapp' folder (`c:\myapp\log` & `c:\myapp\data`)    
 - Create 'db' folder in 'data' folder (`c:\myapp\data\db`)   

### Install `mongod.exe` as service
Open `cmd` as administrator & run command
```
"C:\Program Files\MongoDB\Server\3.6\bin\mongod.exe" --config "C:\Program Files\MongoDB\Server\3.6\bin\mongod.cfg" --install
```
To verify that MongoDB has started successfully, open `c:\myapp\log\mongod.log`    

### Use `mongod.exe` as service
Start Service: `net start MongoDB`    
Stop Service: `net stop MongoDB`    
Remove: `"C:\Program Files\MongoDB\Server\3.6\bin\mongod.exe" --remove`    


