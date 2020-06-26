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

### Organización del contenido del repo

En este apartado se ofrece una vista general de la organización de los ficheros 
de este repositorio.

En general se utiliza la estructura de ficheros generada por `mynt`, la cual se 
explica en su documentación [aquí](https://mynt.uhnomoli.com/docs/quickstart/)

Además, el fichero `requirements.txt` contiene las dependencias del proyecto, y
los ficheros `runtime.txt` y `netlify.toml` sirven para facilitar la configuración
de su despliegue en [netlify](https://www.netlify.com/)


### Configurando el entorno de desarrollo

#### Configuración de Python y de la carpeta del proyecto

**Linux, macOS**

1. Comprueba que Python 3.6 está instalado introduciendo `python --version` en una terminal. 
   Si no lo está, puedes descargarlo en la web [https://python.org](https://www.python.org/downloads/release/python-3610/):
   ```bash
   $ python --version
   Python 3.7.7
   ```

2. (Opcional) Puedes comprobar la ruta donde está instalado Python usando `which python`:
   ```bash
   $ which python
   /usr/local/bin/python
   ```
   Si te aparece un directorio distinto no te preocupes, puede ser normal.

3. Crea una carpeta para el proyecto usando `mkdir pyladiesmadrid`:
   ```bash
   $ mkdir pyladiesmadrid
   ```

4. Posiciónate en ese directorio con `cd pyladiesmadrid`:
   ```bash
   $ cd pyladiesmadrid

   # Comprueba en qué directorio estás (`<YOUR_PATH>` puede ser distinto en
   # cada sistema.)
   $ pwd
   YOUR_PATH/pyladiesmadrid
   ```

¡Estupendo, ya lo tienes!

**Windows**

El proceso es similar al de Linux/mac-OS, pero con algunos comandos distintos.
Es útil tener como referencia la [Tabla de comandos básicos de Powershell](https://devblogs.microsoft.com/scripting/table-of-basic-powershell-commands/).

### Create and activate a virtual environment

1. En el directorio `pyladiesmadrid`, instala el paquete `virtualenv` usando `pip`:

   ```bash
   $ pip install virtualenv
   ```

2. Create nuevo entorno virtual llamado, por ejemplo `venv`:

   ```bash
   $ virtualenv venv
   ```

3. Activa el entorno virtual:

   ```bash
   $ source venv/bin/activate

   (venv)$
   ```

   Tras activar el entorno, debes observar `(venv)` en cada línea nueva de tu consola.

**Nota de error (`AttributeError: 'module' object has no attribute 'X509_up_ref'`):** El error proviene de PyOpenSSL. 
Puede deberse a que tu versión de OpenSSL es demasiado antigua o demasiado nueva. Prueba aumentando o disminuyendo 
la versión de OpenSSL and PyOpenSSL instalada en tu entorno.

### Bifurca (fork) y clona (clone) el repositorio de PyLadies Madrid

1. En GitHub, haz `fork` de http://github.com/pyladiesmadrid/pyladiesmadrid en tu cuenta de Github 
   `<YOUR_GITHUB_USER_NAME>` pressionando el botón de Fork en la esquina superior derecha de la pantalla.
2. En tu directorio local `pyladiesmadrid`, clona el repositorio del que acabas de hacer el fork usando
  `git clone`:

  ```bash
  (venv) $ git clone https://github.com/<YOUR_GITHUB_USER_NAME>/pyladiesmadrid.git
  Cloning into 'pyladiesmadrid'...
  remote: Enumerating objects: 47, done.
  remote: Counting objects: 100% (47/47), done.
  remote: Compressing objects: 100% (29/29), done.
  remote: Total 5877 (delta 22), reused 38 (delta 16), pack-reused 5830
  Receiving objects: 100% (5877/5877), 39.73 MiB | 3.62 MiB/s, done.
  Resolving deltas: 100% (2922/2922), done.
  ```

  Has clonado con éxito el repo de pyladiesmadrid. :smile:

## Ejecutando el site en tu entorno local

**Nota de error** en algunos sistemas operativos, asegúrate de tener las cabeceras para python y libevent
instaladas (p.e., en Ubuntu, **python-dev** y **libevent-dev**). Los paquetes especificados en el fichero
`requirements.txt` son necesarios para que la web se construya con éxito en mynt.

1. Asegúrate de estar en el raíz del repo con el entorno virtual activado:
   ```bash
   (venv) $ pwd
   YOUR_PATH/pyladiesmadrid
   ```
2. Instala las dependencias con `pip`:
   ```bash
   (venv) $ pip install -r requirements.txt

   # Verás cómo se van instalando las distintas librerías en tu entorno
   # No pasa nada si alguna de las versiones es ligeramente distinta a la de este log
   Successfully built hoep MarkupSafe mynt pathtools pycparser PyYAML watchdog
   Installing collected packages: argh, asn1crypto, six, pycparser, cffi, bcrypt, idna, enum34, ipaddress, cryptography, docutils, pyasn1, PyNaCl, paramiko, Fabric, hoep, MarkupSafe, Jinja2, Pygments, PyYAML, pathtools, watchdog, mynt
   Successfully installed Fabric-1.13.1 Jinja2-2.9.6 MarkupSafe-1.0 PyNaCl-1.1.2 PyYAML-3.12 Pygments-2.2.0 argh-0.26.2 asn1crypto-0.22.0 bcrypt-3.1.3 cffi-1.10.0 cryptography-2.0.3 docutils-0.14 enum34-1.1.6 hoep-1.0.2 idna-2.6 ipaddress-1.0.18 mynt-0.3.1 paramiko-2.2.1 pathtools-0.1.2 pyasn1-0.3.2 pycparser-2.18 six-1.10.0 watchdog-0.8.3
   ```

3. Usa mynt para generar y publicar el sitio web en tu entorno local con 
   `mynt gen -f _site && mynt serve _site`:
   ```bash
   (venv) $ mynt gen -f _site && mynt serve _site
   >> Parsing
   >> Rendering
   >> Generating
   Completed in 1.114s
   >> Serving at 127.0.0.1:8080
   Press ctrl+c to stop.
   ```
4. Copia la IP que te indica `mynt` cuando termina de construir el sitio.
   En el log verás algo como `>> Serving at 127.0.0.1:8080`. Después pega la IP
   en la barra de tu navegador para comprobar que el sitio está correctamente desplegado.

**Enhorabuena, ya tienes la web corriendo en tu ordenador** :tada: :snake:

5. (Opcional: A tener en cuenta con cada cambio que realices en el código) 
   Para visualizar los cambios que realices en el código tienes que regenerar la
   web de nuevo. Para ello, pulsa las teclas `crtl` + `c` en la terminal para para
   el servidor que se esté ejecutando, ejecuta el comando del paso 3 y a continuación
   vuelve a refrescar la ventana del navegador web.
