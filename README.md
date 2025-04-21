![Logo_compuesto_vof_2025](https://github.com/user-attachments/assets/df7db686-cfb0-4b47-a125-8cc28e402332)

## Docker-Hadoop

Este repositorio fue utilizado para mostrar el uso de **Hadoop** (con Docker) y **MapReduce** para la materia *Herramientas Avanzadas para el Manejo de Grandes Volúmenes de Datos* de la Licenciatura en Ciencia de Datos para Negocios (LCDN) de la Universidad Nacional Rosario Castellanos (UNRC).

### Pre-requisitos
Tener Docker Desktop instalado.

**Observación:**  
Los comandos utilizados en este repositorio se ejecutaron en los siguientes sistemas operativos:  
* _Windows 11_,  
* _macOS_ (con chip Intel y M2), y  
* _Linux_ (ElementaryOS).

## Hadoop Docker
Para ejecutar los siguientes comandos, debe ubicarse en la carpeta que contenga el archivo `docker-compose.yml`.

### Iniciar el contenedor
Para desplegar el ejemplo de un clúster HDFS, ejecute en la consola de su computadora (según el caso, si es la primera vez o no) lo siguiente:

#### Instalar el contenedor por primera vez
```
docker-compose up
```

#### Levantar el contenedor si ya está instalado
```
docker-compose start
```

### Verificar que el contenedor está trabajando
Para comprobar que el contenedor está en funcionamiento:
```
docker-compose ps
```
Si el estado es `UP`, entonces el contenedor está trabajando correctamente. De lo contrario, ha ocurrido un error al inicializarlo.

### Apagar el contenedor
```
docker-compose stop
```

## Ejemplos de MapReduce
Este repositorio cuenta con los siguientes ejemplos:

* Contar palabras (en la carpeta `MapReduceWordCount`)
* Ordenar datos de temperaturas (en la carpeta `MapReduceTemperature`)
* Resolver sudokus (en la carpeta `MapReduceSudoku`)
* Calcular dígitos de PI (en la carpeta `MapReducePi`)

Las indicaciones sobre cómo ejecutar los ejemplos están en el archivo `README.md` contenido en cada una de las carpetas mencionadas.

## Referencias
* [Notas del curso de Herramientas Avanzadas](https://miguelevangelista.gitbook.io/herramientasavanzadas/instalacion)  
* [Repositorio docker-hadoop](https://github.com/big-data-europe/docker-hadoop)
