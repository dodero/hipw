# Definiciones

En primer lugar, recordemos algunas definiciones estudiadas durante la primera vuelta del curso...

## Internet
: Red informática mundial, descentralizada, formada por la conexión directa entre computadoras mediante el [protocolo HTTP](#protocolo-http) de comunicación.

## World Wide Web
: Conjunto de todas las [páginas web](#página-web) publicadas en cualquier [servidor web](#servidor-web) del mundo.

## Página Web
: Conjunto de informaciones de un [sitio web](#sitio-web) que se muestran en la pantalla de un dispositivo y que puede incluir textos, contenidos multimedia y enlaces (_hipermedia_) con otras [páginas web](#página-web).

## Sitio Web
: Conjunto de [páginas web](#página-web) agrupadas bajo un mismo [nombre de dominio](#nombre-de-dominio) de internet.

## Servidor Web
: Unidad o equipo informático que aloja un conjunto de [páginas web](#página-web) y proporciona acceso a las personas o dispositivos conectados con el servidor a través del [protocolo HTTP](#protocolo-http).

## Protocolo HTTP
: Protocolo de comunicación más empleado en la [World Wide Web](#world-wide-web) para la transferencia de contenidos hipermedia enlazados entre distintas [páginas web](#página-web).

## Dirección IP
: Identificación numérica de un elemento conectado a una red que utiliza el protocolo TCP/IP.

## Nombre de dominio
: Nombre único que identifica a un subárea de [Internet](#internet).

# Dominios DNS

!!! question "¿Cómo llega a localizar un _browser_ dónde está el contenido de una dirección HTTP?"
    Todo equipo o dispositivo conectado a Internet, incluidos los servidores Web, tienen una [dirección IP](dirección-ip) que permite a cualquier otro equipo o dispositivo localizar el servidor web en Internet.

    Las **direcciones IP**, los **servidores** y el sistema **DNS** que traduce las direcciones IP a nombres más afables constituyen la infraestructura básica de software (más allá de los cables, que son hardware) de Internet.
    
    Gracias a esta infraestructura de software, un _browser_ puede localizar un servidor y pedirle la entrega de un determinado contenido web sin tener que conocer la dirección IP del servidor.

El **Sistema de Nombres de Dominio** o _Domain Name System_ (DNS) es un registro mundial, repartido por toda Internet, que permite traducir las direcciones IP de cada servidor en la red a términos memorizables y fáciles de encontrar: los nombres de dominio.

El DNS hace posible que cualquier servicio de la red pueda moverse de un lugar geográfico a otro en la Internet, aún cuando el cambio implique que tendrá una dirección IP diferente, siempre que mantenga registrado el mismo nombre de dominio.

!!! example "Ejemplos de nombres de dominio"

    ```
    icann.org
    bbb.co.uk
    www.uca.es
    meet.jit.si
    ```

???+ info "Cómo funciona el DNS?"
     Visualizar el siguiente video, que explica cómo funcionan los dominios DNS

[![asciicast](./figuras/video-dns.png)](https://www.youtube.com/watch?v=sUhEqT_HSBI)

Sin la ayuda del sistema de nombres de dominio, los usuarios de Internet tendrían que acceder a cada servidor web conociendo la dirección IP del servidor (por ejemplo, sería necesario utilizar http://172.217.10.110/ en vez de http://google.com/).

Además, se reduciría el número de webs posibles, ya que es habitual que una misma dirección IP sea compartida por varios dominios. Por ejemplo, los nombres de dominio `direccioncomercial.wordpress.com` y `gastronomiaatope.wordpress.com` comparten una misma dirección IP.

!!! hint "Averiguar una dirección IP con _nslookup_"
    Para averiguar cuál es la dirección IP a la que DNS traduce un nombre de dominio, puede utilizarse un servicio conocido como **_nslookup_**.

    Como ejemplo, conéctese a http://www.kloth.net/services/nslookup.php e introduzca valores distintos de nombres de dominio: www.uca.es, portalservicios.uca.es, www.elpais.com, direccioncomercial.wordpress.com, gastronomiaatope.wordpress.com, etc. ¿Obtiene IPs distintas para dominios distintos?

## URL frente a nombre de dominio

!!! example "URL versus nombre de dominio"
    El siguiente ejemplo ilustra la diferencia entre una URL (_Uniform Resource Locator_) y un nombre de dominio:

    - Nombre de dominio: `wikipedia.org`
    - URL de un sitio web: `https://www.wikipedia.org`
    - URL de una página web: `https://es.wikipedia.org/wiki/Dominio_de_Internet`

## Dominios de nivel superior

Cuando se creó el sistema de nombres de dominio DNS, el espacio de nombres se dividió en dominios que, leídos de atrás hacia adelante, definen una estructura jerárquica o arbórea de los nombres.

Cualquier nombre de dominio termina en un sufijo .xxx conocido como _top-level domain_ (TLD).

- Hay TLD para dominios territoriales, basados en dos caracteres de identificación de cada territorio de acuerdo a las abreviaciones del ISO-3166 (por ejemplo, `.es`, `.fr`, `.eu`, `.uk`).
- Hay TLD que representan una serie de nombres y multiorganizaciones, según su propósito. Inicialmente, estos dominios fueron: `.com`, `.net`, `.org`, `.edu`, `.gob` y `.mil`. Posteriormente se unieron otros [TLD ampliados](https://www.domain.com/domains/new-domain-extensions#/) como .cafe, .earth, .finance, .life, .market, .video, etc. 

## Ejemplos de nombres de dominio

Los nombres de dominio constan de una secuencia de términos separados por un punto. Cada término es el nombre de un dominio de primer nivel (TLD), de un dominio de segundo nivel, de un subdominio o de un servidor.

| Dominio       | TLD   | Domino de 2º nivel | Subdominio | Servidor |
|:------------- |:-----:|:------------------:|:----------:|:--------:|
| `icann.org`   | `org` | `icann`            |            |          |
| `bbc.co.uk`   | `uk`  | `co`               | `bbc`      |          |
| `www.bbc.com`  | `uk`  | `com`              |            | `www`    |
| `www.bbc.co.uk` | `uk`  | `co`           | `bbc`      | `www`    |
| `www.uca.es`  | `es`  | `uca`              |            | `www`    |

## Organizaciones de registro

El registro de los nombres DNS funciona de forma similar a cualquier otro tipo de registro (registro civil, registro mercantil, registro de la propiedad, etc.), pero con dos diferencias:

1. Es un registro totalmente **digital**: no hay papeles ni oficinas físicas donde ir a registrarse;
2. Es un registro **distribuido**: no hay una única organización centralizada que se encarga de registrar todos los nombres, sino que de cada dominio o subdominio se encarga una organización distinta.

De los dominios TLD se encarga la ICANN, mientras que en cada país hay una organización nacional que se encarga de administrar los subdominios nacionales (`.es`, `.uk`, `.fr`, etc.)

### ICANN
: La _Internet Corporation for Assigned Names and Numbers_ es una organización sin fines de lucro que asigna espacios de direcciones IP, identificadores de protocolo y administra el sistema raíz de servidores y TLD.

### Red.es
: Entidad pública empresarial que gestiona desde el 2000 los subdominios del TLD .es. Antes los gestionaba [RedIris](https://es.wikipedia.org/wiki/RedIRIS).

!!! note "dominios.es"
    En https://www.dominios.es/ puede encontrarse más información sobre el registro de dominios.

Del registro y administración de los subdominios de una empresa o institución se encarga cada organización en cuestión. Por ejemplo, la propia UCA se encarga de los subdominios de `.uca.es`.

Si un particular quiere registrar un dominio, debe acudir a alguno de los registradores autorizados de una entidad administradora. Por ejemplo, si se quiere registrar el dominio `yomismo.es`, puede consultarse la lista de [agentes registradores](https://www.dominios.es/dominios/) de red.es y solicitar el registro, alquilando el nombre de dominio por un período determinado, si es que éste no está ya registrado por alguien.

!!! question "WHOIS: ¿cómo averiguar quién es el arrendatario de un dominio?"
    WHOIS es un protocolo que sirve para consultar quién es el _arrendatario_ (no puede hablarse de _propietario_) de un dominio o de una dirección IP.
    
    La información de WHOIS es pública y dice el arrendatario, la persona de contacto, la fecha de alta, la fecha de caducidad, etc.

!!! example "Consultar WHOIS"
    Como ejercicio, puede consultarse la información de WHOIS de cualquier nombre de dominio en:

    - https://www.internic.net/whois.html
    - https://www.dominios.es/dominios/es/busca-tu-dominio

# Direcciones IP públicas y privadas

???+ info "Recordatorio: qué es una dirección IP"
    Recordar [qué es una dirección IP](https://raiolanetworks.es/blog/que-es-una-direccion-ip/).

No todas las direcciones IP son públicas y globalmente conocidas. Hay un rango de direcciones IP que están reservadas para [redes privadas](https://es.wikipedia.org/wiki/Red_privada) o _intranets_, no accesibles directamente desde fuera de dichas redes. Por ejemplo, las direcciones IP que comienzan por `192.168.x.x` o por `172.x.x.x` son privadas.

!!! question "Un equipo o servidor que tiene una dirección privada, ¿puede publicar en Internet?"
    Sí, pero no directamente. Se necesita una infraestructura adicional que traduzca las direcciones privadas a una pública accesible desde fuera de la red privada.

!!! question "¿Qué dirección me asigna mi proovedor de acceso a Internet?"
    Los proveedores habituales de acceso a Internet (v.g. movistar, orange, vodafone) suelen asignar una única dirección IP pública, y el _router_ caseo asigna direcciones IP privadas a cada equipo. 

    Hagamos una prueba: acceder a https://www.cual-es-mi-ip.net/ desde distintos equipos (móvil, portátil, etc.) de la misma casa y comprobar que en todos se obtiene la misma IP. Ésta es la dirección IP pública que el proveedor no ha asignado temporalmente.

    Si tenemos un equipo en casa con un servidor web instalado, para poder acceder a él desde fuera de casa es necesario configurar el _router_ de una forma determinada para que dicho equipo sea visto desde fuera como si tuviera una dirección IP pública.


<!--
[![asciicast](https://asciinema.org/a/40324.png)](https://asciinema.org/a/40324)
-->