:basketball:
#  Web de Basketball *Onebasket* 

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

- Onebasket se dirigirá a diversos segmentos de audiencia, desde los fanáticos casuales que buscan resúmenes de partidos hasta seguidores apasionados que desean contenido exclusivo detrás de escena y análisis detallados. Estrategias de contenido específicas se diseñarán para cada segmento, maximizando la retención y la participación.

#### Tendencias Emergentes:

- La plataforma abrazará las tendencias emergentes, como transmisiones en vivo de eventos exclusivos, programas interactivos con jugadores y podcasts semanales que analizan las últimas noticias y tendencias del baloncesto. Se implementarán funciones de participación del usuario para atraer a audiencias más jóvenes y activas en las redes sociales.

#### Competencia en el Mercado:

##### Análisis de Competencia:

- Se identificarán plataformas de baloncesto existentes y se evaluará su alcance, calidad de contenido y características distintivas. Onebasket buscará diferenciarse mediante contenido exclusivo, acceso sin precedentes a jugadores y análisis expertos.

##### Colaboraciones Estratégicas:

- Se establecerán alianzas estratégicas con equipos de la NBA, jugadores destacados y marcas deportivas reconocidas para aumentar la visibilidad y la credibilidad. Las colaboraciones incluirán contenido exclusivo, entrevistas y eventos especiales transmitidos en la plataforma.

#### Modelo de Monetización:

Onebasket considerará un modelo híbrido que incluya publicidad no intrusiva, suscripciones premium para acceso exclusivo y colaboraciones con marcas para promociones especiales. Se explorarán oportunidades de venta de mercancía y boletos a eventos a través de la plataforma.

#### Sostenibilidad a Largo Plazo:

- Estrategias de expansión se centrarán en la entrada a mercados emergentes y la adaptación a preferencias culturales locales. Onebasket monitorizará de cerca métricas clave como la retención de usuarios y los ingresos, ajustando estrategias según sea necesario para garantizar la sostenibilidad financiera a largo plazo.

#### Conclusión:

Onebasket busca transformar la pasión por el baloncesto en un éxito sostenible mediante la combinación de contenido atractivo, colaboraciones estratégicas y un enfoque equilibrado en la rentabilidad. Con una visión realista y estrategias bien planificadas, la plataforma aspira a convertirse en el destino preferido para los amantes del baloncesto, asegurando al mismo tiempo su viabilidad económica a largo plazo.

## Base de datos

La [Base de datos](https://github.com/Resultados-deportivos/Documentacion/blob/main/Base_de_datos.md "Base de datos") 

## Web creada en wsgiref

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
Empty

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
