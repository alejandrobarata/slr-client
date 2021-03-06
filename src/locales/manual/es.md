# Manual del Cliente API v.%___PLACEHOLDER_appVersion___%

## 1. El Cliente API

### 1.1 Acerca del Cliente API

El Cliente API es una herramienta de consulta de la Lista Robinson desarrollada por Adigital para las empresas adheridas al Servicio de Lista Robinson. Es una de las tres formas a través de las que una empresa puede consultar la Lista:

1. El Cliente API de Adigital
2. Una herramienta de consulta desarrollada por la propia empresa 
3. Una herramienta de consulta desarrollada por un tercero

El Cliente API te permite comprobar si los ciudadanos a los que tu empresa va a lanzar una acción publicitaria están o no en la Lista Robinson. Está diseñado pensando principalmente en pymes o entidades que no necesiten consultar la Lista Robinson de forma regular y masiva.

Si tu empresa necesita consultar grandes cantidades de registros en la Lista Robinson, te recomendamos realizar un desarrollo propio (opciones 2 y 3) que permita integrar la consulta en los procesos internos de tu empresa de forma más eficiente.

### 1.2 Cómo funciona

Para utilizar el Cliente API deberás:

1.  Preparar un fichero CSV con los datos que deseas consultar
2.  Acceder al Cliente API
2.  Seguir los pasos que el Cliente API va marcando
3.  Guardar los resultados de la consulta

El fichero CSV con los datos que deseas consultar deberá:
 
-  estar codificado en UTF8, 
-  contener los datos de contacto de los destinatarios a los que se vayan a dirigir las acciones publicitarias, y 
-  estar estructurado de la forma en la que se especifica más abajo. 

La separación de las columnas debe ser mediante comas (,) y, opcionalmente, los campos pueden ir entrecomillados por comillas dobles (" ").

### 1.3 Obtener ayuda del Cliente API

En cada pantalla del Cliente API podrás acceder a la sección de este manual que explica qué debes hacer en ese paso pulsando sobre el botón de ayuda que encontrarás en la parte superior derecha:

![Icono de ayuda](manual-helpicon.39x38.png "Icono de ayuda")

### 1.4 Requisitos técnicos mínimos para usar el Cliente API

Para utilizar el Cliente API, se recomienda:

-  Google Chrome versión >71 o Mozilla Firefox >65.
-  4GB de memoria RAM.
-  Conexión de red sin interrupciones.

El número máximo de registros por fichero CSV depende de las características técnicas de tu ordenador. Por lo general, no se recomienda procesar ficheros de más de 500.000 registros. Si el Cliente API se queda sin memoria durante el procesamiento del fichero, los resultados obtenidos se perderán y las consultas habrán sido computadas igualmente, pudiendo derivar en costes adicionales.

<a name='login-help-placeholder'>

## 2. Cómo iniciar sesión en el Cliente API

Para iniciar sesión y acceder al Cliente API, debes disponer de tus claves de acceso API. Si tu empresa está adherida al Servicio de Lista Robinson, puedes obtener las claves siguiendo estos pasos:

1.  Pulsa sobre [este enlace](%___PLACEHOLDER_appSlrHomeUrl___%%___PLACEHOLDER_appSlrGetKeysUrl___%) para acceder a la gestión de la suscripción al Servicio de tu empresa.
2.  En la parte inferior, pulsa el botón “GENERAR ACCESO AL API”:

![Panel generación credenciales API](manual-genapi.567x321.png "Panel de generación de credenciales API")

3.  Se mostrarán tus nuevas claves de acceso a la API en la pantalla:

![Credenciales API generadas](manual-apicreds.567x153.png "Credenciales API generadas")

Si pierdes tus claves API, tendrás que generar unas nuevas. Si quieres que tu navegador las recuerde para no tener que introducirlas de nuevo la próxima vez, activa la casilla ***%___PLACEHOLDER_login.remember-me___%*** e introduce una contraseña. Esta contraseña servirá para proteger tu sesión en este navegador y puede ser distinta a la que utilices en el Servicio de Lista Robinson.

Si no consigues obtener tus claves de acceso, puedes consultar con el equipo de soporte técnico de Adigital en [%___PLACEHOLDER_appEnterpriseContactEmail___%](mailto:%___PLACEHOLDER_appEnterpriseContactEmail___%).

<a name='config-help-placeholder'>

## 3. Cómo consultar la Lista Robinson

Para realizar una consulta a la Lista Robinson, debes seleccionar un fichero CSV con codificación UTF8 que contenga los datos que deseas consultar estructurado según se indica a continuación. No se recomienda que el fichero tenga más de 500.000 registros. Si tienes que consultar un número de registros superior a esa cifra, es recomendable que lo dividas en varios ficheros CSV.

### 3.1 Cómo estructurar el fichero con los datos a consultar

Los ficheros compatibles con el Cliente API de Lista Robinson deben:

-  Estar en formato CSV
-  Los campos deben estar separados por comas y en el orden indicado
-  Opcionalmente, los campos pueden estar entrecomillados con comillas dobles (" ")

Según el canal a través del que se va a desarrollar la acción publicitaria, el fichero debe contener un tipo de datos u otro, de acuerdo con el Anexo I del [Reglamento del Servicio de Lista Robinson](https://www.listarobinson.es/reglamento) y que te resumimos a continuación.

Un mismo fichero no puede combinar distintos tipos de datos. Si tienes que consultar varios canales, deberás hacerlo con distintos ficheros para cada canal.

#### 3.1.1 Campañas publicitarias mediante llamadas telefónicas o SMS/MMS

Si tu empresa va a desarrollar acciones publicitarias a través de llamadas telefónicas o por SMS/MMS, el fichero puede estructurarse de dos maneras distintas:

1. Nombres completos y teléfonos:
    1.  “_Nombre_”
    2.  “_Primer apellido_”
    3.  “_Segundo apellido_”
    4.  “_Teléfono_”
2.  Sólo teléfonos:
    1.  “_Teléfono_”

Por ejemplo:

Nombres, apellidos y teléfonos:

![Ejemplo teléfono nombres y apellidos](manual-phonefull.388x178.png "Ejemplo teléfono nombres y apellidos")

Solo teléfonos:

![Ejemplo solo teléfono](manual-phonesimple.206x163.png "Ejemplo solo teléfono")

#### 3.1.2 Campañas publicitarias mediante correo electrónico

Si tu empresa va a desarrollar acciones publicitarias a través de correo electrónico, el fichero deberá contener sólo direcciones de correo electrónico. Por ejemplo:

![Ejemplo email](manual-email.321x202.png "Ejemplo email")

#### 3.1.3 Campañas publicitarias mediante correo postal

Si tu empresa va a desarrollar acciones publicitarias a través de correo electrónico, el fichero deberá contener los siguientes datos y en el siguiente orden:

1.  Nombre
2.  Primer apellido
3.  Segundo apellido
4.  Nombre de la vía
5.  Número de portal
6.  Código postal
7.  Código de provincia según INE

Es importante que el código de provincia se corresponda con la [tabla de códigos de provincia del Instituto Nacional de Estadística](http://www.ine.es/daco/daco42/codmun/cod_provincia.htm), de lo contrario, la consulta arrojará valores erróneos.

Si el domicilio no tiene número de portal, este debe representarse como "sn", en minúsculas. ***No*** serían válidas, por tanto, fórmulas como: "SN", "sin número", "S/N", etc.

Por ejemplo:

![Ejemplo postal](manual-postal.511x180.png "Ejemplo postal")

#### 3.1.4 Campañas publicitarias a destinatarios cuyo DNI/NIF/NIE es conocido por la empresa

Si tu empresa dispone del DNI/NIF/NIE de los destinatarios y estos son mayores de 14 años, podrás consultar la Lista Robinson mediante DNI/NIF/NIE. Para ello, el fichero deberá contener únicamente los DNI/NIF/NIE de los destinatarios. Por ejemplo:

![Ejemplo dni](manual-dninifnie.187x179.png "Ejemplo DNI/NIF/NIE")

Ten en cuenta que los DNI/NIF siempre deberán estar completos, con sus nueve dígitos y su letra final. Los NIE también deberán contener sus ocho dígitos, su letra inicial y su letra final.

Por ejemplo:

-  Serían válidos:
    -  "12345678A"
    -  "00012345A"
    -  "Y0001234A"
-  ***NO*** serían válidos:
    -  "12345A"
    -  "Y1234A"

#### 3.1.5 Opcional: añadir un identificador en cada registro del fichero CSV

Si en tu empresa asignáis internamente identificadores a vuestros clientes, como puede ser un "número de cliente", puedes incluirlo en el fichero CSV a procesar para poder tratar los resultados después de la consulta con mayor facilidad.

Si decides incluirlo en el fichero CSV, el identificador deberá incorporarse siempre en la primera columna y en todos los registros del fichero CSV. Por ejemplo:

![Ejemplo dni](manual-phonefull-w-customfield.501x178.png "Ejemplo teléfono nombres y apellidos con identificador personalizado")


### 3.2 Cómo iniciar el proceso de consulta

Una vez hayas preparado el fichero CSV con los datos que deseas consultar en la Lista Robinson, tendrás que iniciar sesión, tal y como se describe más arriba en el apartado correspondiente y, una vez dentro de la plataforma, deberás seleccionar el fichero en el Cliente API.

A continuación, deberás indicar el tipo de datos que contiene. El Cliente API tratará de determinar el tipo de datos que contiene el fichero CSV mediante un análisis y te propondrá una opción. **Es importante que revises que el análisis refleja el tipo de datos correcto y, si no es así, lo corrijas**.

Si tu fichero contiene como datos “_teléfonos_” o “_nombres, apellidos y teléfonos_”, también deberás indicar el canal de tu campaña, es decir, si la realizarás mediante llamadas telefónicas o SMS/MMS.

![Tipo de datos del fichero](manual-config.899x596.png "Selección del tipo de datos del fichero")

<a name='progress-help-placeholder'>

## 4. Realización y obtención del resultado de la consulta

Una vez hayas seleccionado en el Cliente API el fichero con los datos a consultar y el tipo de datos que contiene, el fichero será procesado y se iniciará la comparación con la Lista Robinson de acuerdo con las reglas establecidas en el Servicio.

Durante este proceso, el Cliente API leerá el fichero, normalizará los datos, generará los identificadores para la comparación, realizará la consulta de forma seudonimizada y cifrada a la Lista Robinson y recibirá los resultados.

Una vez el Cliente API haya finalizado el proceso, podrás guardar los resultados y comprobar a quién puede tu empresa realizar la acción publicitaria y a quién no.

![Guardado resultados](manual-resultsdownload.893x591.png "Guardado de los resultados")

El Cliente API te entregará los resultados como un nuevo fichero CSV que contiene, por cada registro:

1.  Los datos de tu fichero CSV original
2.  Si el registro está o no en la Lista Robinson
3.  Los sectores publicitarios a los que se ha opuesto el ciudadano al inscribirse en la Lista Robinson
4.  La prueba de la consulta realizada a la Lista Robinson

![Resultados](manual-results.505x178.png "Guardado de los resultados")

Si el registro pertenece a un ciudadano inscrito en la Lista Robinson, se indicará con un "1" en la columna correspondiente, si no consta en la Lista Robinson, con un "0".

Por su parte, los sectores publicitarios se representan por sus "_códigos de sector_". Puedes consultar el código de referencia de cada sector en [este enlace](https://www.listarobinson.es/sectores-publicitarios-y-sus-codigos-api).

Es importante que conserves tanto los registros como la prueba de consulta si quieres que, en el futuro, Adigital pueda emitir un certificado que confirme que has consultado uno o varios de estos registros. Esto puede serte de utilidad, por ejemplo, en el caso de una reclamación por parte de un tercero.

Puedes solicitar un certificado de consulta a Adigital en [%___PLACEHOLDER_appEnterpriseContactEmail___%](mailto:%___PLACEHOLDER_appEnterpriseContactEmail___%).
