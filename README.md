# Zona Fit (GYM) - Gestión de Clientes

Esta es una aplicación web desarrollada con Flask para la gestión de clientes en un gimnasio. Permite registrar, actualizar, eliminar y listar clientes.

## Instalación

Sigue estos pasos para instalar y ejecutar el proyecto en tu máquina local.

### Clona el repositorio

```bash
git clone https://github.com/MainRDSniper09/Zona_Fit_Web
cd tu-repositorio
```

### Crea un entrono virtual

```bash
python3 -m venv venv
source venv/bin/activate  # En Windows usa `venv\Scripts\activate`
```

### Instala las dependencias

Ten en cuenta de tener un archivo 'requirements.txt' en tu proyecto con las siguientes dependencias:

```bash
Flask
mysql-connector-python
WTForms
```

Instala las dependencias con:

```bash
pip install -r requirements.txt
```

### Configura la DB

Asegúrate de tener una base de datos MySQL configurada. Puedes crear una base de datos con el siguiente comando:

```sql
CREATE DATABASE gimasio;
```

### Configura la conexion a la BD

```python
class Conexion:
    _DATABASE = 'gimnasio'
    _USERNAME = 'tu_usuario'
    _PASSWORD = 'tu_contraseña'
    _DB_PORT = '3306'
    _HOST = '127.0.0.1'

    @classmethod
    def obtener_conexion(cls):
        return mysql.connector.connect(
            user=cls._USERNAME,
            password=cls._PASSWORD,
            host=cls._HOST,
            database=cls._DATABASE,
            port=cls._DB_PORT
        )
```

Ya puedes ejecutar la aplicacion usando:

```bash
python app.py
```

La aplicacion se ejecutara en **http://localhost:5000/**

### Uso

Para utilizar la aplicación, abre tu navegador web y ve a http://localhost:5000/. Aquí podrás ver la interfaz para gestionar los clientes del gimnasio.

### Registrar un nuevo cliente
- Completa los campos del formulario con el nombre, apellido y membresía del cliente.
- Haz clic en el botón "Guardar".
### Actualizar un cliente
- Haz clic en el icono de lápiz junto al cliente que deseas editar.
- Modifica la información y haz clic en "Guardar".
### Eliminar un cliente
- Haz clic en el icono de basura junto al cliente que deseas eliminar.

## Contribuir

Si deseas contribuir a este proyecto, sigue estos pasos:

- Haz un fork del repositorio.
- Crea una nueva rama (git checkout -b feature/nueva-caracteristica).
- Haz commit de tus cambios (git commit -m 'Agrega nueva característica').
- Haz push a la rama (git push origin feature/nueva-caracteristica).
- Abre un Pull Request.
