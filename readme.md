---
layout: post.html
---
# PyLadies Madrid

Este sitio web está gestionado por la organizadoras de PyLadies Madrid. 

Este repo está abierto a pull requests de cualquier miembro de la comunidad.

## Resumen

Este es el código de la web https://pyladiesmadrid.netlify.app/. En ella hemos 
utilizado `mynt` para la generación del sitio estático, y está basado en 
🐍 Python 3.6 🐍!

**Contenido**
- [Understanding the repo's directory layout](#understanding-the-repos-directory-layout)
- [Setting up a development system](#setting-up-a-development-system)
- [To add a new PyLadies location](#to-add-a-new-pyladies-location)
- [To write a blog post](#to-write-a-blog-post)
- [To contribute source code to the repository](#to-contribute-to-the-repository)
- [To write a resource](#to-write-a-resource-more-sticky-than-a-blog-post)
- [For Organizers](#for-organizers)
- [License](#license)

### Organización del contenido del repo

En este apartado se ofrece una vista general de la organización de los ficheros 
de este repositorio.

En general se utiliza la estructura de ficheros generada por `mynt`, la cual se 
explica en su documentación [aquí](https://mynt.uhnomoli.com/docs/quickstart/)

Además, el fichero `requirements.txt` contiene las dependencias del proyecto, y
los ficheros `runtime.txt` y `netlify.toml` sirven para facilitar la configuración
de su despliegue en [netlify](https://www.netlify.com/)

```bash
requirements.txt   # file with dependencies used by pip
.circleci          # directory containing the continuous integration configuration settings
fabfile.py         # file which is used by continuous integration for testing and deployment
www                # directory which contains the content of the website
├── CodeOfConduct
├── _assets        # javascript, CSS stuff, and images go here
├── _posts         # contains blog posts written in markdown
├── _templates     # contains the base templates (html and Jinja2) used by the site
├── about
├── archives
├── blog
├── locations      # Use the config.yml file to add new locations or update location info
├── resources
└── sponsor
```