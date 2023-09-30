<p align="center">
  <img src="https://i.imgur.com/oGIGzaN.png" alt="Imagen del proyecto Meteorology Program">
</p>

## Descripci�n
Programa desarrollado en Java con Gradle que lee los CSV de la carpeta data y procesa los datos en una base de datos.
Tras subir los datos del CSV a la base de datos H2, se realizan una serie de consultas utilizando la API Stream:

    - Cada d�a:
        - Lugar de temperatura m�xima.
        - Lugar de temperatura m�nima.
        - Lugar de precipitaci�n m�xima.
        - Precipitaci�n m�xima.

    - Agrupaci�n por provincia y d�a:
        - M�xima temperatura.
        - M�nima temperatura.
        - Media de temperatura.
        - Precipitaci�n m�xima y lugar.
        - Precipitaci�n media.
        - Lugares donde ha llovido.

    - Lugar donde m�s ha llovido.

    - Datos de una provincia (por cada d�a):
        - Temperatura m�xima, m�nima y d�nde ha sido.
        - Temperatura media m�xima.
        - Temperatura media m�nima.
        - Precipitaci�n m�xima y d�nde ha sido.
        - Precipitaci�n media.


Para terminar, el programa exporta los datos de la base de datos de una provincia a un CSV.

## ? Instrucciones de uso
- ? **.env:** Este fichero se deber� de crear en la carpeta resources con los siguientes datos:

        DATABASE_USER=usuario
        DATABASE_PASSWORD=contrase�a
  Deber�s de modificar el usuario y la contrase�a que quieres que tenga la base de datos. La raz�n por la que el .env no se agrega al repositorio es por motivos de seguridad. Estos datos est�n aislados del database.properties.

- **database.properties:** Este fichero es el que se deber� modificar si se quiere cambiar la URL, el driver, el nombre de la base de datos o si se quiere forzar el reinicio de la tabla en el inicio del programa (eliminar� y volver� a crear la tabla).

## ? Tecnolog�as
- Java 11.
- Gradle.
- Lombok.
- H2 Database.
- dotenv-kotlin.
- Gson.
- MyBatis.
- Logback Classic.

## Estructura
- Adapters: Adaptadores para poder exportar los datos de fechas y tiempo correctamente.
- Controllers: El controlador de Meteorology. Aqu� se realizan las consultas API Stream de Meteorology y tambi�n las consultas a la base de datos.
- Exceptions: Se almacenan todas las excepciones personalizadas del programa.
- Models: Clases POJO y DTO (para facilitar el proceso de transferencia de datos).
- Repositories: El manejo de consultas CRUD para interactuar con la base de datos.
- Services: Servicios de la aplicaci�n. 
  - CRUD: Maneja la l�gica de las consultas CRUD.
  - Database: Administrar la base de datos y sus conexiones.
  - IO: Entrada y salida de datos. el CSVManager administra el importado de los datos en CSV y el ExportManager la exportaci�n a JSON.
- Utils: Clases de utilidad. En UtilParsers se encuentran todos los m�todos de parseo. ApplicationProperties la clase que se encarga de cargar los archivos de propiedades (en este programa, database.properties).
- Main: Clase principal del programa.
- MeteorologyApp: La clase que se encarga de ejecutar toda la l�gica del programa. Se le llama en el Main de la aplicaci�n.

## Autores
- [�ngel (Madirex)](https://github.com/Madirex)
- [Rub�n (Rubenoide03)](https://github.com/Rubenoide03)