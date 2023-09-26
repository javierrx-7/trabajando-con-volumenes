# volumenes
# Descarga la imagen 'httpd' y comprueba que está en tu equipo.

    Para ello utilizamos el comando docker pull httpd para descargar la imagen httpd.

# Crea un contenedor con el nombre 'asir_httpd'.
# Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.
# Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.
# Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/
    Para crear el contenedor utilizaremos esta linea de comando el mapeo del puerto 80 y por ultimo montar el htdocs utilizamos esta linea de comandos: docker run -dit --name asir_httpd -p 8000:80 -v /home/asir2/Escritorio/SRI/paginas:/usr/local/apache2/htdocs/ httpd:2.4


# Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.
    Para esto debemos crear una hoja html guardandola en la carpeta donde esta el contenedor creado y arrancado:

    http://localhost:8000/pagina.html
    <html>
    <head>
    </head>
    <body>
    <h1>Hola mundo</h1>
    <img src="https://i.pinimg.com/originals/db/79/1c/db791c6d62ba7ec5635264f8533152cd.gif">
    <img src="https://gifdb.com/images/high/lightning-mcqueen-holding-breath-cars-5a6h77oagg3x4kmw.gif">
    </body>
    </html>


# Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000
    docker run -dit --name asir_web1 -p 8000:80 -v /home/asir2/Escritorio/SRI/web:/usr/local/apache2/htdocs/ httpd:2.4


# Utiliza Code para hacer un hola mundo en html
    http://localhost:8000/web1.html
    <html>
    <head>
    </head>
    <body>
    <h1>Hola mundo</h1>
    <img src="https://media.tenor.com/fHC-d9SfRDwAAAAM/meme-star-wars.gif">
    <br>
    <img src="https://media.tenor.com/ttHHjTphRhwAAAAd/fast-and-furious-the-fast-and-the-furious.gif">
    </body>
    </html>


# Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.
    docker run -dit --name asir_web2 -p 9080:80 -v /home/asir2/Escritorio/SRI/web2:/usr/local/apache2/htdocs/ httpd:2.4


# Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:
    http://localhost:9080 

    http://localhost:8000


# Tienen que salir la misma página web
