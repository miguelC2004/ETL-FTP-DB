# Automatización de Descarga y Concatenación de Archivos Excel desde FTP

Este script en Python está diseñado para automatizar la descarga de archivos Excel desde un servidor FTP, concatenar los datos de los archivos descargados en un archivo base local y opcionalmente insertar los datos concatenados en una base de datos MySQL.

## Funciones Principales

### connect_ftp(host, username, password)
Establece una conexión FTP con el servidor especificado.

### get_most_recent_filename(ftp, prefix)
Obtiene el nombre del archivo más reciente en el servidor FTP que coincide con un prefijo dado.

### download_file(ftp, filename, local_path)
Descarga un archivo del servidor FTP al directorio local especificado.

### connect_db()
Establece una conexión con la base de datos MySQL, sea en local o en servidor.

### insert_data_to_db(data)
Inserta datos en una tabla específica de la base de datos.

### concatenate_files(base_file_path, new_file_path, insert_into_db=False)
Concatena los datos del archivo nuevo al archivo base local y opcionalmente inserta los datos en la base de datos.

## Flujo Principal

1. Conexión al servidor FTP.
2. Obtención del nombre del archivo más reciente.
3. Descarga del archivo si no existe localmente.
4. Concatenación de datos si el archivo base existe.
5. Opcionalmente, inserción de datos concatenados en la base de datos.
6. Cierre de la conexión FTP.

## Configuración

- `ftp_host`: Dirección del servidor FTP.
- `ftp_username`: Nombre de usuario para iniciar sesión en el servidor FTP.
- `ftp_password`: Contraseña para iniciar sesión en el servidor FTP.
- `local_download_path`: Directorio local donde se descargan los archivos.
- `base_file_path`: Ruta del archivo base donde se concatenan los datos.
- `file_prefix`: Prefijo para filtrar los archivos en el servidor FTP.

## Uso

1. Modificar las variables de configuración según las credenciales.
2. Ejecutar el script realizar el proceso de ETL.

## Documentación Adicional

### Requerimientos

- Python 3.12
- ftplib, datetime, openpyxl, os, mysql.connector, re (librerías de Python).

### Compatibilidad

Este script está diseñado para funcionar en entornos donde se tenga acceso a un servidor FTP y una base de datos MySQL, en IDE PyCharm.

### Seguridad

- Asegúrese de mantener seguras las credenciales de acceso al servidor FTP y a la base de datos.
- Considere encriptar las credenciales o utilizar métodos seguros para su gestión.
