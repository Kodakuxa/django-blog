# Nest Mart & Grocery Blog

Nest Mart & Grocery es una aplicación web construida con Django: blog con categorías y posts, autenticación de usuarios, búsqueda, subida de archivos/media, y un panel de administración (dashboards) para gestionar contenido como un blog.

Tecnologías: Django, Python, Django Crispy Forms, Pillow, Sass/CSS estático.

---

## Requisitos

- Python 3.10 o superior (se recomienda 3.11+)
- pip (incluido con Python)
- virtualenv (opcional pero recomendado)

Dependencias:

- `Django==5.0.4`
- `asgiref==3.11.0`
- `crispy-bootstrap5==2025.6`
- `django-crispy-forms==2.5`
- `pillow==10.3.0`
- `sqlparse==0.5.5`
- `tzdata==2025.2`

---

## Instalación y ejecución

1. Clonar el repositorio y entrar en la carpeta del proyecto:

```bash
git clone <repo-url>
cd django-blog
```

2. Crear y activar un entorno virtual:

```bash
python -m venv env
source env/bin/activate  # macOS / Linux
```

Windows (PowerShell):

```powershell
python -m venv env
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\env\Scripts\Activate.ps1
```

Windows (cmd.exe):

```cmd
env\Scripts\activate.bat
```

3. Instalar dependencias:

```bash
pip install -r requirements.txt
```

4. Aplicar migraciones y crear superusuario:

```bash
python manage.py migrate
python manage.py createsuperuser
```

5. Ejecutar el servidor de desarrollo:

```bash
python manage.py runserver
```

## Scripts y comandos útiles

- `python manage.py runserver` — inicia el servidor de desarrollo
- `python manage.py migrate` — aplica migraciones pendientes
- `python manage.py makemigrations` — genera nuevas migraciones
- `python manage.py createsuperuser` — crea un usuario administrador
- `python manage.py collectstatic` — recopila archivos estáticos para producción
- `python manage.py test` — ejecuta tests

---

## Estructura

```
.
├─ db.sqlite3
├─ manage.py
├─ requirements.txt
├─ blog_enterprise/          
│  ├─ settings.py
│  ├─ urls.py
│  └─ views.py
├─ blogs/                    
│  ├─ models.py
│  ├─ views.py
│  ├─ urls.py
│  └─ templates/
├─ dashboards/               
├─ env/                      
├─ media/                    
└─ templates/                
```

Descripción breve de las carpetas principales:

- `blog_enterprise/`: paquete del proyecto Django (configuración, enrutado global).
- `blogs/`: app que contiene modelos de `Post`, `Category`, vistas para listar y mostrar posts, formularios y urls.
- `dashboards/`: vistas y plantillas administrativas orientadas a gestión (crear/editar posts y categorías).
- `templates/`: plantillas Jinja/Django usadas por las vistas.
- `static/` y `media/`: activos estáticos (CSS/JS/imagenes) y archivos subidos por usuarios.

---

## Rutas y comportamiento

- `/` — página principal (vista `views.home` en `blog_enterprise.views`).
- `/index.html` — alias de la página principal.
- `/category/<int:category_id>/` — posts por categoría (`blogs.views.posts_by_category`).
- `/blog/<slug:slug>` — detalle de un post (`blogs.views.blogs`).
- `/blogs/search/` — búsqueda de posts (`blogs.views.search`).
- `/register/`, `/login/`, `/logout/` — registro y autenticación (vistas en `blog_enterprise.views`).
- `/dashboard/` — rutas del panel de administración (incluye `dashboards.urls`).

Ruta por defecto: ` / ` (home).

---

## Capturas de pantalla

- Inicio / Lista de posts

<img width="1864" height="901" alt="image" src="https://github.com/user-attachments/assets/031f8470-3383-4460-92e1-4ce5c3cbdb90" />
<img width="1847" height="894" alt="image" src="https://github.com/user-attachments/assets/d8298558-afbc-4546-a840-a1af40135304" />

- Vista de post (detalle)

<img width="995" height="898" alt="image" src="https://github.com/user-attachments/assets/98714eb7-2b8e-4794-99f4-2977469b1ce8" />

- Login / Registro

<img width="1435" height="778" alt="image" src="https://github.com/user-attachments/assets/549c91b1-0d5b-4476-b527-59cc9a315426" />


