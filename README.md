
# medear

El propósito del paquete `medear` es facilitar el trabajo con los datos
utilizados en el proyecto MEDEA3, y proporcionar las funciones con las
que se obtuvieron dichos datos, así como otras que simplifiquen nuestra
labor.

Concretamente, el paquete incluye los datos de población por sexo y
grupos de edad a nivel de sección censal para el periodo 1996-2016 así
como la cartografía para las ciudades implicadas en el proyecto, también
a nivel de sección censal. Los datos para algunos años están encriptados
por tratarse de consultas específicas realizadas al INE y solo son
accesibles mediante contraseña. Los datos desde 2004 hasta 2016 son de
libre acceso siguiendo la licencia del INE, y se pueden obtener usando
las funciones contenidas en este paquete.

El paquete también dispone de una serie de rutinas para geocodificar
direcciones, de forma que no es necesario salir de `R` en ningún
momento. En el apartado de viñetas del paquete podrás consultar los
diversos protocolos que se vayan creando (actualmente ya está disponible
el protocolo de geocodificación.)

Del mismo modo, y una vez ya se disponga de la mortalidad geocodificada,
también se incluye una función para la detección de agrupaciones
anómalas de defunciones en comparación con los `n` puntos más próximos,
lo que permite detectar errores sistemáticos en la geocodificación y
aborda el problema de la detección de centros residenciales.

## Instalación

El paquete `medear` se puede instalar desde GitHub con:

``` r
if (!"devtools" %in% installed.packages())
  install.packages("devtools")
devtools::install_github("fisabio/medear", build_vignettes = TRUE)
```

**IMPORTANTE**: si trabajas desde un ordenador conectado a la red a
través de un *proxy*, es muy importante que te asegures de que tu
conexión esté bien configurada. Para ello debes ejecutar esta serie de
comandos (sustituyendo el texto por los valores apropiados de tu centro:
pregunta al servicio de informática):

``` r
if (!"httr" %in% installed.packages())
  install.packages("httr")
httr::set_config(
  httr::use_proxy(
    url      = "xxx.xxx.xxx.xx",
    port     = 0000,
    username = "usuario",
    password = "clave"
  )
)
```

## Otros usos del paquete

Aunque el paquete surge como respuesta a una necesidad de un proyecto de
investigación, consideramos que las herramientas pueden ser útiles para
todo aquel que:

1.  quiera extrapolar el proyecto MEDEA3 a otras ciudades,
2.  trabaje con secciones censales en un marco temporal que abarque
    varios años,
3.  intente geocodificar direcciones y no quiera salir del entorno R,
4.  utilice poblaciones por sección censal en sus cálculos.

Es por ello que se ha intentado dejar bastante abiertos los argumentos
de las funciones, con lo que no será difícil adaptar su uso a otros
fines.

## Participación: dudas y consultas

Para cualquier comentario, duda o consulta que se desee realizar, se
puede abrir un [*Issue*](https://github.com/fisabio/medear/issues) en
este repositorio de GitHub.

Si deseases aportar algo al proyecto, puedes modificar el código a tu
antojo y abrir un [*Pull
Request*](https://github.com/fisabio/medear/pulls) en el repositorio.

Por último, y si quieres contactar directamente en caso de tener
problemas para instalar el paquete o acerca de su uso, puedes dirigirte
a Carlos Vergara en la dirección de correo <vergara_car@gva.es>: él te
orientará acerca de los pasos a seguir.
