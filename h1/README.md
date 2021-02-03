# Práctica 1

Business intelligence homework

* [Instructions](iInstructions)
* [Getting Started](#getting-started)
  * [Built with](built-with)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [About](#about)
  * [Directory Tree](#directory-tree)
  * [Usage](#usage)
  * [Things to take into consideration](#things-to-take-into-consideration)

## Instructions

Utilizando lo aprendido en clase con docker, debe en su computadora levantar una base de datos y si lo desea un ambiente con jupyter y python que pueda acceder a la base de datos.
Luego deberá utilizar los 4 archivos que se le compartieron en la carpeta Práctica 1 dentro del drive de la clase, y deberá realizar un ETL sobre cada uno de los archivos. El ETL debe ser trabajado en jupyter notebooks y debe leer el archivo y realizar todo el proceso de inserción a la base de datos, tomando en cuenta que debe poder procesar de ser necesario.

Los entregables son:

* 4 archivos de notebooks de júpiter (extensión ipynb), uno por cada archivo compartido
* 4 archivos sql que contenga el script de creación de cada una de las tablas que creo para cada archivo
* El docker-compose file que utilizó para su base de datos y/o ambiente de python. No es obligatorio utilizar el contenedor de Jupyter
* Todo esto lo deberá subir a un repositorio en Github y su entregable será el link al repositorio

## Getting Started

### Built With

* jupyter notebooks
* docker-compose

### Prerequisites

* docker-compose

### Installation

Clone the repo

```sh
    git clone https://github.com/LinddM/bi012021.git
```

## About

### Directory Tree

```
    │   docker-compose.yml
    │   README.md
    │
    ├───covid19
    │       covid19.csv
    │       covid19.ipynb
    │
    ├───data
    │       data.ipynb
    │       data.parquet
    │
    ├───sql
    │       covid19.sql
    │       data.sql
    │       transactions.sql
    │       vaccinations.sql
    │
    ├───transactions
    │       transactions.ipynb
    │       transactions.json
    │
    └───vaccinations
            vaccinations.csv
            vaccinations.ipynb
```

Basically you'll find each ETL (.ipynb) with its raw (csv, parquet*, json) data in a different folder to keep order. SQL scripts are stored in the sql folder
<i>* parquet file is not included in this repository because it's too heavy</i>

## Usage

Start the containers

```sh
    docker-compose up
```

## Things to take into consideration

1. Used local jupyter notebooks (not in a container) but connected to mysql with the container

2. Used data.parquet file but not uploaded to github due to its size

3. Loaded only 100 rows to data.sql (data.parquet) because my computer couldn't handle the processing of the entire dataframe
