![Logo_compuesto_vof_2025](https://github.com/user-attachments/assets/df7db686-cfb0-4b47-a125-8cc28e402332)

## Docker-Hadoop
Este repostiorio fue utilizado para mostrar el uso de **Hadoop** (con Docker) y **Map Reduce** para la materia de Herramientas Avanzadas para el Manejo de Grandes Volumenes de Datos de la Licenciatura en Ciencia de Datos para Negocios (LCDN) de la Universidad Nacional Rosario Castellanos (UNRC).

### Pre-requisitos
Tener Docker Desktop instalado

**Observacón:**  
Los comandos utilizados en este repositorio se ejecutaron en los sistemas operativos: 
* _Windows 11_,
* _MacOs (con chip Intel y M2)_ y
* _Linux (ElementaryOS)_. 

## Hadoop Docker
Para ejecutar los siguientes comandos debe estar en la carpeta que contenga el archivo `docker-compose.yml`

### Inciar el contendor
Para deployar el ejemplo de un cluster HDFS ejecutar en la consola de su computadora (depende el caso, si es primera vez o no) lo siguiente:

#### Instalar el contendor por primera vez
```
  docker-compose up
```
#### Levantar el contenedor si ya esta instalado
```
  docker-compose start
```

### Vefiricar que el contenedor esta trabajando
Ver si el contenedor esta trabajando
```
  docker-compose ps
```
Si el estado es `UP`, entonces el contenedor está trabajando correctamente. De caso contrario ha ocurrido un error al inicializar el contenedor.

### Apagar el contendor
```
  docker-compose stop
```

## Ejemplos de MapReduce
Este repositorio cuenta con los siguientes ejemplos: 

* Contar palabras (en la carpeta `MapReduceWordCount`)
* Ordenar datos de temperaturas (en la carpeta `MapReduceTemperature`)
* Resolver sudokus (en la carpeta `MapReduceSudoku`)
* Calcular digítos de PI (en la carpeta `MapReducePi`)

Las indicaciones de como ejecutar los ejemplos, estan en el archivo `README.md` contenidos en las carpetas antes menciondas.

## Referencias
* [Notas del curso de Herramientas Avanzadas ](https://miguelevangelista.gitbook.io/herramientasavanzadas/instalacion)
* [Repositorio docker-hadoop](https://github.com/big-data-europe/docker-hadoop)
