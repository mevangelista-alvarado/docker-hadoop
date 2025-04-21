## MapReduce Temperature
Ejemplo de MapReduce para ordenar temperaturas de mayor a menor.

## Pre-requisitos
Para ejecutar los siguientes comandos, debe ubicarse en la carpeta que contenga el archivo `docker-compose.yml`.

## Mover el archivo .jar y el puzzle.dta
Mueva el archivo `hadoop-mapreduce-examples-2.7.1-sources.jar` ejecutando: 
```
  docker cp ./MapReduceSudoku/hadoop-mapreduce-examples-2.7.1-sources.jar namenode:/tmp
```

Mueva el archivo `Temperature.txt` ejecutando: 
```
  docker cp ./MapReduceSudoku/Temperature.txt namenode:/tmp
```

## Ejemplo Map Reduce
* Para entrar al nodo de Hadoop debemos ejecutar,  
```
  docker exec -it namenode bash
```
* Luego,
```
  hdfs dfs -mkdir /user/root/input_temperaturas
```
* Después,
```
  cd tmp
```
* Ejecutar
```
  hdfs dfs -put Temperature.txt /user/root/input_temperaturas
```
* Por último,  
```
  hadoop jar hadoop-mapreduce-examples-2.7.1-sources.jar org.apache.hadoop.examples.SecondarySort input_temperature output_temperature
```

## Ver los resultados
* Ejecutar,  
```
  hdfs dfs -cat /user/root/output_temperaturas/*
```
* Luego,  
```
  hdfs dfs -cat /user/root/output_temperaturas/part-r-00000 > /tmp/temperaturas_resultado_ordenadas.txt
```
* Ejecutar,
```
  exit
```
* Por último,  
```
  docker cp namenode:/tmp/temperaturas_resultado_ordenadas.txt ./MapReduceTemperature/
```

Ahora el archivo de texto esta en la carpeta `./MapReduceTemperature/`.

## Docs
* [Ordenar números de menor a mayor](https://miguelevangelista.gitbook.io/herramientasavanzadas/ejemplos-de-mapreduce/ordenar-numeros-de-menor-a-mayor-temperaturas)
