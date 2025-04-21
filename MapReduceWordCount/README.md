## MapReduce WordCount
Ejemplo de MapReduce para contar palabras de un archivo de texto.

## Pre-requisitos
Para ejecutar los siguientes comandos, debe ubicarse en la carpeta que contenga el archivo `docker-compose.yml`.

## Mover el archivo .jar y el puzzle.dta
Mueva el archivo `hadoop-mapreduce-examples-2.7.1-sources.jar` ejecutando: 
```
  docker cp ./MapReduceWordCounthadoop-mapreduce-examples-2.7.1-sources.jar namenode:/tmp
```

Mueva el archivo `el_quijote.txt` ejecutando: 
```
  docker cp ./MapReduceWordCount/el_quijote.txt namenode:/tmp
```

## Ejemplo Map Reduce
* Para entrar al nodo de Hadoop debemos ejecutar,  
```
  docker exec -it namenode bash
```
* Luego,
```
  hdfs dfs -mkdir /user/root/input_contador
```
* Después,
```
  cd tmp
```
* Ejecutar
```
  hdfs dfs -put el_quijote.txt /user/root/input_quijote
```
* Por último,  
```
  hadoop jar hadoop-mapreduce-examples-2.7.1-sources.jar org.apache.hadoop.examples.WordCount input_contador output_contador
```

## Ver los resultados
* Ejecutar,  
```
  hdfs dfs -cat /user/root/output_contador/*
```
* Luego,  
```
  hdfs dfs -cat /user/root/output_contador/part-r-00000 > /tmp/quijote_result.txt
```
* Ejecutar,
```
  exit
```
* Por último,  
```
  docker cp namenode:/tmp/quijote_result.txt ./MapReduceWordCount/
```

Ahora el archivo de texto esta en la carpeta `./MapReduceWordCount/`.

## Docs
* [Contar palabras](https://miguelevangelista.gitbook.io/herramientasavanzadas/ejemplos-de-mapreduce/contar-palabras)
* [https://hadoop.apache.org/docs/stable/hadoop-mapreduce-client/hadoop-mapreduce-client-core/MapReduceTutorial.html](https://hadoop.apache.org/docs/stable/hadoop-mapreduce-client/hadoop-mapreduce-client-core/MapReduceTutorial.html)
