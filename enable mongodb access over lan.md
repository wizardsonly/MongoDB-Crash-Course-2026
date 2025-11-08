
To enable MongoDB to accept connections from other computers, the following steps are required:

    Modify the MongoDB Configuration File:
        Locate the mongod.conf file. On Linux systems, it is typically found at /etc/mongod.conf. On Windows, it is usually in C:\Program Files\MongoDB\Server\<version>\bin\mongod.cfg.
        Open the file with a text editor.
        Find the net: section and specifically the bindIp: parameter.
        Change the bindIp value to 0.0.0.0 to allow connections from all IP addresses, or specify a comma-separated list of specific IP addresses if you want to restrict access to certain machines. 

Code

    net:
      port: 27017
      bindIp: 0.0.0.0 # Or specify specific IPs like 192.168.1.10, 10.0.0.5

Save and close the configuration file.

    Restart the MongoDB Service:
        After modifying the configuration file, restart the MongoDB service to apply the changes. 

On Linux: ```bash sudo systemctl restart mongod ```
On Windows: Restart the MongoDB service through the Services manager.