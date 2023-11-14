
#  Web de Basketball *Onebasket* :basketball:

1. [Descripción General](#descripción-general)
2. [Rentabilidad](#rentabilidad)
3. [Base de datos](#base-de-datos)
4. [Web creada en wsgiref](#web-creada-en-wsgiref)
5. [Api creada en ApiFast](#api-creada-en-apifast)
6. [Configuración del servidor](#configuración-del-servidor)
7. [En versiones futuras](#en-versiones-futuras)

## Descripción General
Este proyecto utiliza Python y WSGI para crear una aplicación web que gestiona información relacionada con deportes, incluyendo publicaciones, eventos, jugadores, usuarios, ligas, estadios, equipos, likes, registros, comentarios y puntos.

## Rentabilidad
### Visión Empresarial:
La visión de nuestra plataforma, "Onebasket," es convertir la pasión global por el baloncesto en un éxito sostenible, aprovechando no solo la popularidad del deporte, sino también las oportunidades económicas que ofrece. Este análisis se centrará en dos aspectos clave: el potencial de visitantes y la competencia en el mercado.

### Cantidad de Posibles Visitantes:

#### Demanda Global:

- Con más de 400 millones de fanáticos en todo el mundo, el baloncesto presenta una demanda global sólida, especialmente en regiones como América del Norte, Europa y Asia. La diversidad geográfica del deporte brinda a Onebasket la oportunidad de atraer a una audiencia global.

#### Segmentación de Audiencia:

- Onebasket se dirigirá a diversos segmentos de audiencia, desde los más casuales que buscan resúmenes de partidos hasta seguidores apasionados que desean contenido exclusivo detrás de escena y análisis detallados. Estrategias de contenido específicas se diseñarán para cada segmento, maximizando la retención y la participación. Se busca configurar para cada usuario el contenido que el haya clicckado y reaccionado más.

#### Tendencias Emergentes:

- La plataforma abrazará las tendencias emergentes, como transmisiones en vivo de eventos exclusivos, programas interactivos con jugadores y podcasts semanales que analizan las últimas noticias y tendencias del baloncesto. Se implementarán funciones de participación del usuario para atraer a audiencias más jóvenes y activas en las redes sociales. En veriones futuras.

#### Competencia en el Mercado:

##### Análisis de Competencia:

- Las noticias del baloncesto están cubierto cubiertas por la prensa de manera local, fijando un los los target por territorio, un ejemplo claro son nba.com o feb.es(Federaciín española de baloncesto), pero el resto de ligas Europeas, Asiaticas y Amateurs no tienen una Web que cubra todas sus noticias y menos aún sus partidos. 
##### Colaboraciones Estratégicas:

- Se establecerán alianzas estratégicas con equipos de la NBA, jugadores destacados y marcas deportivas reconocidas para aumentar la visibilidad y la credibilidad. Las colaboraciones incluirán contenido exclusivo, entrevistas y eventos especiales transmitidos en la plataforma.

#### Modelo de Monetización:

Onebasket considerará un modelo híbrido que incluya publicidad no intrusiva, suscripciones premium para acceso exclusivo y colaboraciones con marcas para promociones especiales. Se explorarán oportunidades de venta de mercancía y boletos a eventos a través de la plataforma, una vez todo lo anterior haya salido adelante. 

#### Sostenibilidad a Largo Plazo:

- Estrategias de expansión se centrarán en la entrada a mercados emergentes y la adaptación a preferencias culturales locales. Onebasket monitorizará de cerca métricas clave como la retención de usuarios y los ingresos, ajustando estrategias según sea necesario para garantizar la sostenibilidad financiera a largo plazo.

## Base de datos

La [Base de datos](https://github.com/Resultados-deportivos/Documentacion/blob/main/Base_de_datos.md "Base de datos") 

## Web creada en wsgiref
Reporsitorio del la Web creada siguiendo la estructura MVC, [aquí](https://github.com/Resultados-deportivos/web "Web").

### Métodos de Inserción

Se han proporcionado métodos para insertar datos en cada una de las tablas mencionadas anteriormente. Estos métodos facilitan la incorporación de nueva información al sistema.

#### CRUD de la Aplicación

Se ha implementado un conjunto de operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para cada entidad del sistema. Estas operaciones permiten gestionar eficientemente la información almacenada en la base de datos.

#### Operaciones CRUD

1. **Crear (Create)**
    - `insert_publicacation_data(data)`: Crea una nueva publicación con los datos proporcionados.
    - `insert_event_data(data)`: Crea un nuevo evento con los datos proporcionados.
    - `insert_player_data(data)`: Crea un nuevo jugador con los datos proporcionados.
    - `insert_user_data(data)`: Crea un nuevo usuario con los datos proporcionados.
    - `insert_league_data(data)`: Crea una nueva liga con los datos proporcionados.
    - `insert_stadium_data(data)`: Crea un nuevo estadio con los datos proporcionados.
    - `insert_team_data(data)`: Crea un nuevo equipo con los datos proporcionados.
    - `insert_likes_data(data)`: Crea un nuevo like con los datos proporcionados.
    - `insert_register_data(data)`: Crea un nuevo registro con los datos proporcionados.
    - `insert_commentas_data(data)`: Crea un nuevo comentario con los datos proporcionados.

2. **Leer (Read)**
    - `get_all_publicaciones()`: Obtiene todas las publicaciones almacenadas.
    - `get_all_eventos()`: Obtiene todos los eventos almacenados.
    - `get_all_jugadores()`: Obtiene todos los jugadores almacenados.
    - `get_all_usuarios()`: Obtiene todos los usuarios almacenados.
    - `get_all_ligas()`: Obtiene todas las ligas almacenadas.
    - `get_all_estadios()`: Obtiene todos los estadios almacenados.
    - `get_all_equipos()`: Obtiene todos los equipos almacenados.
    - `get_all_likes()`: Obtiene todos los likes almacenados.
    - `get_all_registros()`: Obtiene todos los registros almacenados.
    - `get_all_comentarios()`: Obtiene todos los comentarios almacenados.

### VIEWS.PY

Variables globales
`user_info` -> A través de las cookies se guardarán en este diccionario </br>
Get template -> `page = env.get_template('page_example.html')`

#### Función ejemplo para renderizar

'''python
def page_example(environ, start_response):
    # Get data from models
    publicaciones = get_posts()
    # This response the html with the data and render own css
    response = index.render(publicaciones=publicacionescss_name='inicio.css').encode('utf-8')
    status = '200 OK'
    response_headers = [('Content-type', 'text/html')]
    start_response(status, response_headers)
    return [response]
'''
### MODELS.PY
Todas las funciones creadas consumen la API con GET para consumir los datos en JSON, PUT para insertaciones o actualizaciones, y DELETE. 
### CONTROLLER.PY
En el controller se llama a las funciones creadas en views y se configurán las rutas del navegador.
### UTILITIES.PY
Funciones costumizadas para enviar email, definir nuevas contraseñas...

### FLASH_MANAGER.PY
Clase y metodos de add y get para mostrar mensajes popup en py.

## Api creada en ApiFast
Reporsitorio del la API creada con FastAPI, [aquí](https://github.com/Resultados-deportivos/api "API").
### Código Python para una API FastAPI con SQLAlchemy y PostgreSQL
#### Importaciones de módulos y paquetes
```python
from datetime import datetime, date, time
from hashlib import sha256
import databases
import sqlalchemy
from fastapi import FastAPI, HTTPException, Request, Query
from passlib.hash import sha256_crypt
from pydantic import BaseModel
from sqlalchemy import Table, Column, Integer, String, Boolean
from sqlalchemy.util import asyncio
from starlette.middleware.cors import CORSMiddleware
```
#### Configuración y ejecución de la aplicación FastAPI

```python
if __name__ == "__main__":
    import uvicorn
    uvicorn.run("controladorApi:app", host="localhost", port=8080, reload=True)
```
##### Configuración de la aplicación FastAPI y middleware CORS
```python
app = FastAPI()
origins = ["*"]  # Deberías especificar los orígenes permitidos
app.add_middleware(
    CORSMiddleware,
    allow_origins=origins,
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"]
)
```
#### Configuración de la base de datos PostgreSQL y definición de la tabla 'jugadores'
```python
database_name = "eusko_basket"
user = "*"
password = "*"
host = "pgsql03.dinaserver.com"
port = "5432"
DATABASE_URL = f"postgresql://{user}:{password}@{host}:{port}/{database_name}"
database = databases.Database(DATABASE_URL)
metadata = sqlalchemy.MetaData()
players = Table(
    "jugadores",
    metadata,
    Column("id", Integer),
    Column("nombre", String(255)),
    Column("apellido", String(255)),
    Column("fechanacim", String(12)),
    Column("equipoid", Integer),
    Column("altura", String(50)),
    Column("peso", String(50)),
    Column("numero", Integer),
)
```
##### Definición del modelo Pydantic 'jugadores'
```python
class jugadores(BaseModel):
    nombre: str
    apellido: str
    fechanacim: str
    equipoid: int
    altura: str
    peso: str
    numero: int
```
##### Configuración y desconexión de la base de datos en los eventos de inicio y apagado
```python
@app.on_event("startup")
async def startup_db_client():
    await database.connect()
@app.on_event("shutdown")
async def shutdown_db_client():
    await database.disconnect()
Endpoint para obtener jugadores con filtros opcionales
python
@app.get("/basket/players")
async def get_players(id: int = Query(None), nombre: str = Query(None), equipoid: int = Query(None), num: int = Query(None)):
    query = "SELECT * FROM jugadores"
    conditions = []
    params = {}
    if id is not None:
        conditions.append("id = :id")
        params['id'] = id
    if nombre is not None:
        conditions.append("nombre = :nombre")
        params['nombre'] = nombre
    if equipoid is not None:
        conditions.append("equipoid = :equipoid")
        params['equipoid'] = equipoid
    if num is not None:
        query += f" LIMIT {num}"
    if conditions:
        query += " WHERE " + " AND ".join(conditions)
    comments = await database.fetch_all(query, values=params)
    return comments
```
##### Endpoint para crear un nuevo jugador
```python
@app.post("/basket/players")
async def create_player(player: jugadores):
    fechaNacim = datetime.strptime(player.fechanacim, "%Y-%m-%d").date()
    query = players.insert().values(
        nombre=player.nombre,
        apellido=player.apellido,
        fechanacim=fechaNacim,
        equipoid=player.equipoid,
        altura=player.altura,
        peso=player.peso,
        numero=player.numero
    )
    await database.execute(query)
    return {"nombre": player.nombre, **player.dict()}

```
##### Endpoint para actualizar la información de un jugador
```python
@app.put("/basket/players/{player_id}")
async def update_player(player_id: int, player: jugadores):
    fechaNacim = datetime.strptime(player.fechanacim, "%Y-%m-%d").date()
    query = players.update().where(players.c.id == player_id).values(
        nombre=player.nombre,
        apellido=player.apellido,
        fechanacim=fechaNacim,
        equipoid=player.equipoid,
        altura=player.altura,
        peso=player.peso,
        numero=player.numero
    )
    await database.execute(query)
    return {"message": "Información del jugador actualizada exitosamente"}
```
##### Endpoint para eliminar un jugador por ID
```python
@app.delete("/basket/players/{player_id}")
async def delete_player(player_id: int):
    query = players.delete().where(players.c.id == player_id)
    await database.execute(query)
    return {"message": f"El jugador con ID {player_id} ha sido eliminado"} '''
Este código define una API FastAPI que interactúa con una base de datos PostgreSQL para realizar operaciones CRUD en una tabla de jugadores de baloncesto.
```
## Configuración-del-servidor
[Aquí](https://github.com/Resultados-deportivos/Documentacion/tree/main/Servidor "Servidor") en tres PDF todos los configuraciones y registros del Servior DINAHOSTING y AWS. 

## En versiones futuras
### VALIDAR CON REGEX
La mayoría de formularios tienen una validación sencilla creada por el HTML, en versiones futuras se validarán todas con Regex como, por ejemplo, un nivel mínimo de seguridad para las contraseñas.
### CRUD PARA UN USUARIO MISMO
Cuando el usuario inicia sesión, se podrá configurar su avatar a su gusto.
### PROTECCION PATH
Ahora mismo hay vulnerabilidades en la web, en versiones futuras la mayoría de los paths estarán protegidos.
### Buscador especifico 
La búsqueda por un jugador o equipo específico vendrá en versiones posteriores



:busts_in_silhouette: JULIO,ISSAM, JOKIN, DIEGO, IKER
