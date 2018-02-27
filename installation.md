## Windows
Download: [MongoDB](https://www.mongodb.com/download-center?jmp=nav#community) & Install msi.   

Go: `C:\Program Files\MongoDB\Server\{version}`. Create folder conf & create file `mongod.cfg`    
`conf/mongod.cfg`
```
systemLog:
    destination: file
    path: c:\myapp\log\mongod.log
storage:
    dbPath: c:\myapp\data\db
```
Details: [Configuration File Options](https://docs.mongodb.com/manual/reference/configuration-options/)

Create 'myapp' folder in C drive. Create log & data folder in 'myapp'    

Open cmd as administrator run command
```
"C:\Program Files\MongoDB\Server\3.6\bin\mongod.exe" --config "C:\Program Files\MongoDB\Server\3.6\conf\mongod.cfg" --install
```
