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
To verify that 'MongoDB' has added successfully as service, open `c:\myapp\log\mongod.log`    
```
2018-02-27T07:20:15.075-0700 I CONTROL  [main] Trying to install Windows service 'MongoDB'
2018-02-27T07:20:15.078-0700 I CONTROL  [main] Service 'MongoDB' (MongoDB) installed with command line '"C:\Program Files\MongoDB\Server\3.6\bin\mongod.exe" --config "C:\Program Files\MongoDB\Server\3.6\bin\mongod.cfg" --service'
2018-02-27T07:20:15.079-0700 I CONTROL  [main] Service can be started from the command line with 'net start MongoDB'
```

### Use `mongod.exe` as service
Start service: `net start MongoDB`
```
C:\>net start MongoDB
The MongoDB service is starting.
The MongoDB service was started successfully.
```
Stop service: `net stop MongoDB`    

Remove: `"C:\Program Files\MongoDB\Server\3.6\bin\mongod.exe" --remove`    

### Connect to MongoDB
 - Add environment variable: `C:\Program Files\MongoDB\Server\3.6\bin`
 - Open cmd and run command: `mongo` (`mongo.exe` is the mongo shell in bin folder, since we added environment variable, cmd will recognize `mongo` command)


