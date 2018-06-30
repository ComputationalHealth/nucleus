# nucleus
- Launch baikal-devenv through docker-compose (tested against tag v2.6.0.3)
```shell
git clone git@github.com:ComputationalHealth/baikal-devenv.git
cd baikal-devenv/compose
docker-compose up -d --build
```
- Run HDFS startup.sh config script
```shell
docker exec hadoop-namenode /bin/bash startup.sh
```
- Load Jupyter in browser, upload demo files (from generator folder)
- Import NiFi flow via browser (port 8080)

- Load Zeppelin (port 9001)
	- Add Avro dependency/artifact to Spark interpreter: com.databricks:spark-avro_2.11:4.0.0
	- Import notebook from analytics/NucleusAnalytics.json