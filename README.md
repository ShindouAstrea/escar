# Sitio web ESCAR de Carabineros de Chile.

Esta es la repo de Sitio web de ESCAR, desarrollado por nosotros. Consiste en 2 sitios: El portal y el Gestor.

Este documento se hizo a modo de documentación ... bastante rápida, con la finalidad que sea útil, pero sin ninguna garantía.

## Información base

- PHP 7 (migrado de PHP 5).
- Base de datos MySQL
- CodeIgniter 2 aparentemente.
- ESCAR y Gestor_Escar deben estar juntos (en el filesystem) si lo tienes en producción. Entre los 2 hacen hartas cosas hardcodeadas que se rompen si los dejas en carpetas distintas. 
- Tiene un buscador basado en 

## ¿Que tienen las carpetas?

- **ESCAR:** Web de escar. Es la parte publica, y en carabineros sale para afuera (internet).
- **Gestor_Escar:** El gestor de la web de escar. Este no sale para afuera, solo se mantiene de forma interna (intranet).
- **boton-pago:** Pagina que implementa el boton de pago de la api de banco estado.
- **Otros:** Cachibaches de utilidad como la base de datos, la capacitación, y una estructura de proyecto para montarlo en docker. 

## ¿Los login cuales son?

Según lo que me encontré en la base de datos, los login para el Gestor son:

- suser/admin
- (????)

## ¿Donde configuro esto para montarlo por ahí?

La configuración global para ambos sitios esta en Gestor_Escar/config.php. La configuración se divide dependiendo del entorno donde quieras implementarlo (escuelacarabinerostest.carabineros.cl, gestor.escar.test o gestor.escar.centos.test). Dependiendo de cada categoría, deberás configurar base de datos y dominio a utilizar. 

Nota: Podrías revisar ESCAR/seach/config/database.php, que corresponde a la config del motor de búsqueda. En teoría debería estar conectado a la config base, pero cuando recibí el zip con el proyecto esto estaba seteado manual (y lo otro comentado).

Los próximos pasos no son necesarios si no les cambias el nombre a las carpetas de cada proyecto, pero si lo haces, pues:

- Configura ESCAR/config.php, y setea $DIRECTORY_ESCAR_MANAGER con el nombre de la carpeta del gestor.



Una cosa que es importante es que donde sea donde lo montes, la carpeta de la web y el gestor deben estar juntas siempre, no importa donde, pero deben estar juntas (de todas formas, en la web se hace un chequeo (en ESCAR/config.php que lo llama index.php) para verificar que esté todo ok); tal como ya estan en el GIT.

## Un poco de historia de este proyecto.

### Los inicios

ESCAR fue un proyecto de la consultora años luz atrás, (2012-2013 creo?) donde se armó la base del sitio y el gestor, terminando con éxito.

### El lavado de cara

Varios años después (2019), nos contactaron para darle un lavado de cara al sitio y actualizar sus componentes. Felipe Diaz fue el responsable de ello, donde actualizó la base del código, skin, entre otros, tratando de dejar el gestor lo mas posible en su  estado original (se agregaron módulos extras). 

### ¿Y Ahora?

Bueno, Felipe se fue de la consultora, y dejó una carpeta en Google Drive con los archivos del proyecto. Estos fueron migrados al Git donde estas tu ahora mismo. 

