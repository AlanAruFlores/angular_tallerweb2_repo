# Modelo Cliente Servidor
modelo que usamos para acceder y obtener recursos 

## Cliente
El navegador donde el cual reaalizamos la peticion

## Servidor
Programa que se ejecuta en un servidor fisico para ofrecer servicios al cliente. 

Para comunicarse entre el cliente y servidor deben comunicarse mediante un formato de intercambio de datos (JSON)
El protocolo HTTP define dicho formato:

# Protocolo HTTP (Hyper text transfer protocol)
Conjunto de reglas que permiten transmitir informacion entre dispositivos de rede

## Solicitudes http
Las request o solicitudes http que realiza el cliente hacia el servidor tienen el siguiente formato:
    .METODOS HTTP --> Accion que debe realizar hacia el servidor
    .CAMINO (PATH) --> Donde esta el recurso
    .VERSION DE HTTP
    .CABECERAS (HEADERS) --> provee mayor informacion al servidor
    .CUERPO (BODY) --> contiene la informacion que debe ser enviada al servidor  para procesar la solicitud (JSON)
    No se incluye en todas las solicitudes, solo en el verbo POST Y PUT

## Metodo Http
El cliente debe especificar el verbo http, que especifica la accion a realizar o la intencion de la solicitud:
    .GET  (Verbo para solicitar un recurso especifico)  
    .POST (Para crear un recurso especifico)
    .PUT  (Para modificar un recurso especifico)
    .DELETE (Para eliminar un recurso)

## Respuestas HTTP
El servidor cuando procesa la solicitud o request y luego genera un response. Dicho response tiene una estructura:
    .Codigo de estado (Indica si la respuesta fue exitosa)
    .Texto de estado (Para describir el codigo)
    .Version de HTTP
    .Cabeceras
    .Cuerpo 

## Codigos HTTP
Son esenciales para que el cliente sepa que paso con la solicitud en el servidor
    .Respuestas Informativas (100-199)
    .Respuestas Satisfactorias (200-299)
    .Redirecciones(300-399)
    .Errores de los clientes(400-499)
    .Errores de los servidores (500-599)

## Puerto
Ubicacion virtual del S.O por la cual se puede acceder a una aplicacion o proceso especifico que se este
ejecutando en ese puerto.

## URL (Uniform Resource Locator)
Direccion de un recurso en la web

## Subdominio
Permite a los sitios web organizar y separar la infromacion para distintos propositos
  ejemplo : www , blog, 
  www.ejemplo.com

## Dominio
Referencia unica a un sitio web

## Routing
Es un concepto clave para el desarrollo de servidores en cualquier plataforma. Consiste en manejar las peticiones
del cliente en base a ciertos criterios: metodo y ruta
    .Metodo: De esta manera el servidor sabra que operacion realizar (GET,POST,PUT,DELETE)
    .Ruta: El servidor sabra el recurso especifico
Una ruta es la combinacion entre metodo y ruta.


# Express 
Como vimos en el ejemplo de routing usando NodeJS:
````js
//Si estamos en al pagina inicial
    if(url === "/"){
        res.statusCode = 200;
        res.end("Bienvenido a mi primer servidor y API con Node");
    }

    //Si la url es /cursos,  devuelvo los datos
    else if(url === "/cursos"){
        res.statusCode = 200;
        res.end(JSON.stringify(infoCursos)); // mando los datos en un JSON
    }

    else if(url === "/cursos/programacion"){
        res.statusCode = 200;
        res.end(JSON.stringify(infoCursos.programacion));
    }

    res.statusCode = 404;
    res.end("No se halla dicho recurso");
````
La aplicacion puede ser muy compleja , entonces se hace uso del framework de Express en lugar de escribir
la parte del servidor con nodejs.


# EXTRA
## REST Client 
Este plugin permite testear 