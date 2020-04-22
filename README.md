# HDFS Sequence file expander
##### Hey guys have you came across a situation where you need to see data in the sequence files saved in HDFS, well that may seems to be a very specific usecase but if you have to do it this utility would help you.
* Just export the following `env`and run `sbt run` or you may simple make a jar using `sbt assembly` to run it on multiple places
* You just need to export the following env vars
```shell script
  export HDFS_URL=hdfs://localhost:9000 #default
  export HDFS_USER=hadoop
  #DESTINATION_FOLDER must end with a "/"
  export DESTINATION_FOLDER="/some-local-path/"
  #top most path which has the the sequence file
  export HDFS_DIR="/"

  ```
  
  #### Note
  * For `HDFS_DIR` the top level directory is required, it will find all the sequence files under it directories may also contain files other then sequence file but that's okay, given that in case you just need to expand one file you may simple give the absolute path to the sequence file for `env` var `HDFS_DIR`
  
  ##Quick Test
  * For a quick test you may pull this image `shuhamknoldus/hdfs-container:3.2.1` the `user` in this image is root so you may run 
  `docker run -p9000:9000 -p9870:9870 shuhamknoldus/hdfs-container:3.2.1` then you can simply use this without having to setup HDFS locally
  * After saving you can save some sequence file in to the hdfs
  * Using  
  ```shell script
export HDFS_URL=hdfs://localhost:9000 
  export HDFS_USER=hadoop
```
as hdfs parameters
  
  Feel free to report any bugs/enhancement :)  