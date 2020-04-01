#### An Ambari Service for Hue
Ambari service for easily installing and managing Hue 3.x on HDP 2.x cluster.  This repository is updated with only the minimal changes required
for Kyle's original repo to install.  If you need to understand the differences please diff each repo.

#### Authors
  - [Kyle Joe](https://github.com/EsharEditor)
  - [Steven Matison](https://github.com/steven-dfheinz)

#### Notes
- A big thank you to Kyle for creating the original HDP 2.x github repo. Have a look here:  https://github.com/EsharEditor/ambari-hue-service

- See https://gethue.com for more information, versions, and official documentation.
- DFHz working on Hue 4.x with HDP 3.x [HERE](https://github.com/steven-dfheinz/HDP3-Hue-Service)
- DFHz working on Hue Management Pack for Ambari [HERE](https://github.com/steven-dfheinz/dfhz_hue_mpack)

#### Version
- Hue 3.11.0
- HDP 2.x

#### Setup
- Install required services: HDFS,Yarn,Hive,Hbase,Spark,Zookeeper,Sqoop,Oozie and execute python command below before installing Hue.
- Install epel repository OR Make sure all gethue dependencies are able to be installed on hue node
- Deliver Service Fileset to Ambari   
``` 
sudo git clone https://github.com/steven-dfheinz/HDP2-Hue-Service.git /var/lib/ambari-server/resources/stacks/HDP/[version]/services/HUE
```
  **** be sure to get your correct [version] for command above
- To change to any other Hue Version, replace '3.11.0' with your required version in the following files:
```
metainfo.xml
package/scripts/params.py
package/scripts/setup_hue.py
```
- Restart Ambari
```
service ambari-server restart
```
- In Ambari click on 'Add Service' and install HUE

#### Known Issues
- Very long install time due to compile time for Hue's make install command

#### Coming Soon
- HDP 2.x Management Pack [dfhz_hue_mpack](https://github.com/steven-dfheinz/dfhz_hue_mpack)
