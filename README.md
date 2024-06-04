## minio
docker-compose.yml
```
version: '3.7'

services:
  minio:
    image: minio/minio
    container_name: minio
    ports:
      - "9000:9000"
      - "9001:9001"
    environment:
      MINIO_ROOT_USER: root
      MINIO_ROOT_PASSWORD: 12345678
    command: server /data --console-address ":9001"
    volumes:
      - minio_data:/data

volumes:
  minio_data:
```

## JAR
prepare jar files in `./jars`
```
['./jars/hadoop-aws-3.3.2.jar', './jars/aws-java-sdk-bundle-1.11.1026.jar', './jars/iceberg-spark-runtime-3.5_2.12-1.5.2.jar', './jars/mysql-connector-j-8.4.0.jar']
```


## start pyspark notebook
`./run.sh`