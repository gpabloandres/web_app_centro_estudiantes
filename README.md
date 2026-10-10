# Centro de Estudiantes

Aplicación Flask modular para el sitio público y su panel de administración. Todo el código desplegable vive en la raíz: `app/`, `config.py`, `wsgi.py` y `requirements.txt`.

El prototipo HTML previo se conserva como referencia en `docs/prototipo_lista_27.html`; no forma parte de la aplicación servida.

## Desarrollo

Desde la raíz del repositorio:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
flask --app 'app:create_app' init-db
flask --app 'app:create_app' create-admin
flask --app 'app:create_app' run
```

En Windows, activa el entorno con `.venv\Scripts\Activate.ps1`. Define una `SECRET_KEY` estable antes de usar datos reales. SQLite guarda la base de datos en `instance/centro_estudiantes.db`.

## Pruebas

```bash
python -m unittest discover -v
```

## PythonAnywhere gratuito

Consulta [gu_a_de_despliegue_en_pythonanywhere.md](gu_a_de_despliegue_en_pythonanywhere.md). El plan gratuito funciona con SQLite local. En el panel Web apunta el WSGI a `wsgi.py`, instala `requirements.txt` en el virtualenv y establece una `SECRET_KEY` estable antes de importar `application`.

Inicializa las tablas y crea un administrador con los comandos CLI anteriores. No se crea una contraseña por defecto.
