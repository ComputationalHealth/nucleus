nucleus
=======
This repository includes code and applications that can be generate random, normally-distributed laboratory data and feed it into a data science platform for use in creating business intelligence and advanced analytic applications.

Instructions
------------

- Launch [baikal-devenv](https://github.com/ComputationalHealth/baikal-devenv) through docker-compose (tested against tag v2.6.0.3)
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
- Open NiFi via browser (port 8080)
  - Import Nucleus NiFi flow (nifi/Nucleus_Processor.xml) -- the hl7-parser.py script is already included in the flow
  - Start the processor group in NiFi

- Load Zeppelin (port 9001)
  - Add Avro dependency/artifact to Spark interpreter: com.databricks:spark-avro_2.11:4.0.0
  - Import notebook from analytics/NucleusAnalytics.json
