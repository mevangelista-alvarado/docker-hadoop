## MapReduce Sudoku
Ejemplo de MapReduce para resolver un Sudoku

## Pre-requisitos
Para ejecutar los siguientes comandos, debe ubicarse en la carpeta que contenga el archivo `docker-compose.yml`.

## Mover el archivo .jar y el puzzle.dta
Mueva el archivo `hadoop-examples-0.20.205.0.jar` ejecutando: 
```
  docker cp ./MapReduceSudoku/hadoop-examples-0.20.205.0.jar namenode:/tmp
```

Mueva el archivo `puzzle1.dta` ejecutando: 
```
  docker cp ./MapReduceSudoku/puzzle1.dta namenode:/tmp
```

## Ejemplo Map Reduce
* Para entrar al nodo de Hadoop debemos ejecutar,  
```
  docker exec -it namenode bash
```
* Luego,
```
  cd tmp
```
* Ejecutar,  
```
  hadoop jar hadoop-examples-0.20.205.0.jar sudoku puzzle1.dta
```

## Ver los resultados
* Ejecutar,  
```
  hadoop jar hadoop-examples-0.20.205.0.jar sudoku puzzle1.dta > solucion_puzzle.txt
```
* Luego,  
```
  exit
```
* Por último,  
```
  docker cp namenode:/tmp/solucion_puzzle.txt ./MapReduceSudoku/
```

Ahora el archivo de texto esta en la carpeta `./MapReduceSudoku/`.

## Docs
* [Resolver Sudoku](https://miguelevangelista.gitbook.io/herramientasavanzadas/ejemplos-de-mapreduce/resolver-sudoku)
* [https://hadoop.apache.org/docs/stable/api/org/apache/hadoop/examples/dancing/package-summary.html](https://hadoop.apache.org/docs/stable/api/org/apache/hadoop/examples/dancing/package-summary.html)
