# Pour Lancer le cluster spark-haddop
```
-cd compose
-docker-compose build
-docker-compose up -d
-docker-compose scale slave=n
```

# Pour arréter le cluster
```
docker-compose down
```

# Pour faire des tests
```
cd spark
```

#Test PiCount
```
./spark-2.2.3-bin-hadoop2.7/bin/spark-submit --class Pack.PiCount --master spark://127.0.0.1:7077 ./CountSpark.jar 100
```

#Test WordCount
```
./spark-2.2.3-bin-hadoop2.7/bin/spark-submit --class Pack.WordCount --master spark://127.0.0.1:7077 --files filesample.txt ./CountSpark.jar
```


