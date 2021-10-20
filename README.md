# YOTA-EA.github.iopepassaco?tab=repositories

Este es el repositorio de la web de YOTA-EA. Está creada con [gohugo](https://gohugo.io/), [Markdown](http://es.wikipedia.org/wiki/Markdown) y `HTML/CSS`.

## ¿Cómo está desarrollada?

La plantilla está creada con `HTML/CSS/BOOTSTRAP`, aunque cada página individual está escrita en markdown con la idea de simplificar su creación y mantener un estilo uniforme en toda la web.

**La plantilla se trata de un submódulo de git alojada [aquí](https://github.com/gethugothemes/bookworm-light)**, cuando se clone el repositorio hay que escribir: 

`git clone https://github.com/YOTA-EA/YOTA-EA.github.io.git --recursive`

## Trabajando con la web

En esta sección se explicará brevemente cómo subir posts o realizar modificaciones a la web de YOTA-EA

### 1. Instalar Hugo

Para instalar Hugo en tu máquina Linux escribe en el terminal `sudo snap install hugo` o `sudo apt install hugo`.

Para más información: [Install Hugo](https://gohugo.io/getting-started/installing/)


### 2. Hacer un fork del repositorio

Para poder enviar tu trabajo a la página web tendrás que copiar el repositorio global a tu usuario personal (hacer un fork), realizar en esta copia tus cambios, y, una vez estés seguro de que todo funciona correctamente, enviarlos al repositorio global para que sea revisado por algún admin y se añada a la página web.

Para hacer esto:

1. Crea una copia del repositorio original (`YOTA-EA/YOTA-EA.github.io`) en tu cuenta de usuario, esto se llama hacer un *fork*. Para ello pulsa el botón llamado *cuchillo* o *fork*:

![Botón fork](./static/man/fork.png)

2. Aparecerá en pantalla alguna información referente al *fork*. Con lo que estamos haciendo, crearemos una copia exacta (de la web en el momento en el que haces el fork) en tu usuario.

![Botón fork](./static/man/fork2.png)

3. Clona ("descarga") tu fork del repositorio en tu ordenador. Para ello vete a tu cuenta de GitHub, busca el fork que acabas de hacer, haz click en el botón verde que dice "Code", pulsa HTTPS, y luego copia la URL que te darán. La URL será de la forma `https://github.com/TU_USUARIO/YOTA-EA.github.io.git`:

![Link clonar](./static/man/clone1.png)

Abre una terminal ejecuta, cambiando `URL_REPO_FORK` con la URL anteriormente copiada:
    
```
$ git clone --recursive URL_REPO_FORK
```
Ya tienes una copia de la web en tu pc sobre la que realizar los cambios. 


### 3. Realiza los cambios o actualizaciones

#### ¿Cómo añadir un nuevo post al blog?

Para añadir una nueva actividad a la página web, crea un nuevo fichero con el formato `YYYY-MM-DD-Nombre-actividad.md` en la carpeta `content/blog/`. Por ejemplo:

```
2021-09-10-Taller-Arduino.md
```

Y las carpetas quedarán de la forma:

```
├── content
│   ├── blog
│   │   ├── 2021-09-10-Taller-Arduino.md
```

Modifica el fichero a tu antojo con la información de la actividad. 

**Ten en cuenta que el fichero debe adoptar el formato de Markdown.** Para facilitar esta tarea, se encuentra un fichero de ejemplo en la carpeta `examples/` que se puede usar como plantilla. Además, existen [herramientas online](https://demo.hedgedoc.org/) que permiten editar y visualizar ficheros markdown en directo.


## Añadiendo imágenes

Si quieres añadir imagenes en tu página, **crea una carpeta** en `static/images/post/` cuyo nombre coincida con el del fichero correspondiente del post en el que van a ir las imágenes sin la terminación `.md`. Una vez creada, ya puedes meter las imágenes en la carpeta `static/images/post/NOMBRE_DEL_FICHERO_DEL_POST/`. 

Para referenciar las imágenes en el post, introduce la siguiente línea:

```
![Descripción de la imagen](images/post/NOMBRE_DEL_FICHERO_DEL_POST/imagen1.jpg)
```


## Añadiendo ecuaciones matemáticas

Las ecuaciones matemáticas se hacen con MathJax **siguiendo la sintaxis de LaTeX**.

Cuando quieras añadir una ecuación matemática, hazlo de la siguiente forma:

```
<div>
$$
\sqrt{\frac{\lambda}{\ro}}
$$
</div>
```

En hugo actualmente hay problemas con el `_`, que se utilizan para los subíndices , tienes que escribirlo de la forma `$ 2\_{asdf} $` o `$ var_ 2$`.

Para escribir ecuaciones *in line* se haría así: `Estamos hablando de un tema de \\( \lambda /2 \\)`





### 5. Visualiza los cambios ejecutando la web de forma local en tu ordenador

```
$ cd YOTA-EA.github.io/
$ hugo server
```

En la salida del comando, te dirá que la web está montada en **localhost**, en algún puerto (normalmente, `localhost:1313`). Abre esa web desde el navegador y revisa tus cambios. Comprueba que todo está en orden.
    
### 6. Sube los cambios a tu repositorio

Tan simple como ejecutar los siguientes comandos:

```
$ git add .
$ git commit -m "COMENTARIO CON LO QUE HAS CAMBIADO"
$ git push
```

### 7. Envía una solicitud de cambios al repositorio global de YOTA-EA

Para enviar los cambios al repositorio *global* tendrás que crear un **Pull Request**, es decir, una petición para que tus cambios se añadan al servidor, con el visto bueno de algún administrador. Ve a tu repositorio y pulsa:

    ![Pull Request](./static/man/PR.png)

    Eso te llevará a una pestaña donde tienes describir los cambios que has realizado. Pulsa en el botón *Crear Pull Request*, y tus cambios se enviarán al repositorio global. Cuando alguien le de el visto bueno, tus cambios se subirán a la web.

    ![Enviar Pull Request](./static/man/PR2.png)

