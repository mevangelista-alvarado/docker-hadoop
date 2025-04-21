## MapReduce Pi
Ejemplo de MapReduce para calcular los digítos de Pi

## Pre-requisitos
Para ejecutar los siguientes comandos, debe ubicarse en la carpeta que contenga el archivo `docker-compose.yml`.

## Mover el archivo .jar 
Mueva el archivo `hadoop-mapreduce-examples-2.7.1-sources.jar` ejecutando: 
```
  docker cp ./MapReducePi/hadoop-mapreduce-examples-2.7.1-sources.jar namenode:/tmp
```

## Ejemplo Map Reduce
* Para entrar al nodo de Hadoop debemos ejecutar,  
```
  docker exec -it namenode bash
```
* Luego ejecute,  
```
  hdfs dfs -mkdir /user/root/input_pi
```
* Ejecutar,  
```
  hadoop jar hadoop-mapreduce-examples-2.7.1-sources.jar org.apache.hadoop.examples.pi.DistBbp 10 1 2 x 2 input_pi output_pi
```

## Ver los resultados
* Ejecutar,  
```
  hdfs dfs -cat /user/root/output_pi/part-r-00000 > /tmp/pi.txt
```
* Luego,  
```
  exit
```
* Por último,  
```
  docker cp namenode:/tmp/output_pi.txt ./MapReducePi/
```

Ahora el archivo de texto esta en la carpeta `/MapReducePi`.

## Docs
* [Calcular decimales de pi](https://miguelevangelista.gitbook.io/herramientasavanzadas/ejemplos-de-mapreduce/calcular-decimales-de-pi)
* [https://hadoop.apache.org/docs/stable/api/org/apache/hadoop/examples/pi/package-summary.html](https://hadoop.apache.org/docs/stable/api/org/apache/hadoop/examples/pi/package-summary.html)

