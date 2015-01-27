# provider.MaxFileSystemUsage - blumeta

## What I check is...

Try to find what is consuming space in the meta volume and what the current rate of consumption is.  

FIXME: to be filled in with what we know


## How I check it is...

df 
du -sk /blumeta0


## What I mean when I break...

There is high disk concumption on the dashDB meta data volume /blumeta0.  If the rate of disk consumption continues, the metadata volume will become full and the provider will have unpredictable behavior for existing users and for provisioning.  

The most common cause of this problem is that there is one ore more user workloads generating a large volume of DB2 log records.  The DB2 archive logs are staged on blumeta0 before being backed up to Swift storage.   


## How you fix me is...

If a DB2 user or application can be identified terminate the users session using FIXME [Bowen's script]


## Special Considerations - 


