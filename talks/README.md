---
layout: post.html
---
# Web de PyLadies Madrid - Biblioteca de Charlas

La página de biblioteca de charlas recoge charlas que han sido realizadas por mujeres de la comunidad Python,
ya sea en meetups de PyLadies Madrid o en otras conferencias o eventos.

## Cómo añadir una nueva charla

Para añadir una nueva charla hay que hacer dos cosas:

- Crear una nueva página en `_containers/talks`(../_containers/talks)
- Añadir la imagen para la miniatura en `_assets/images/talks`(../_assets/images/talks)

El formato que usamos para los nombres de archivo es el siguiente:
```
AAAA-MM-DD-palabras-clave-titulo-charla
```

Toda la información de la página de charla se encuentra en la cabecera. La plantilla es:

```
---
layout: talk.html
title: "Inserta el título aquí"
authors:
    - name: "Nombre PyLady 1"
      url: "URL al perfil en RRSS (opcional)"
    - name: "Nombre PyLady 2 (opcional, borrar si solo hay una, añadir más si hay más de dos)"
      url: "URL al perfil en RRSS de PyLady 2 (opcional)"
image: images/talks/<pon la ruta a la imagen que has añadido>
video: <URL del vídeo (típicamente: https://www.youtube.com/embed/XXXXXXXXX)>
date: <DD/MM/AAAA>
tags: [tag1, tag2]
---
```

Una vez la tengas, comprueba que todo se ve bien en tu local (instrucciones [aquí](../#ejecuta-el-site-en-tu-entorno-local)), y después haz una Pull Request para que se publique en la web. ¡Muchas gracias por tu contribución! :)
