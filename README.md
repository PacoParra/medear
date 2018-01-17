
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

## Instalación

`medear` se puede instalar desde GitHub con:

``` r
if (!"devtools" %in% installed.packages())
  install.packages("devtools")
devtools::install_github("fisabio/medear", build_vignettes = TRUE)
```

**IMPORTANTE**: si trabajas desde un ordenador conectado a la red a
través de un *proxy*, es muy importante que te asegures de que tu
conexión esté bien configurada, para lo cual debes ejecutar esta serie
de comandos (sustituyendo el texto por los valores apropiados de tu
centro: pregunta al servicio de informática):

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

## Participación: dudas y consultas

Para cualquier comentario, duda o consulta que se desee realizar, se
puede abrir un [*Issue*](https://github.com/fisabio/medear/issues) en
este repositorio de GitHub.

Si deseases aportar algo al proyecto, puedes modificar el código a tu
antojo y abrir un [*Pull
Request*](https://github.com/fisabio/medear/pulls) en el repositorio.

Por último, y si quieres contactar directamente en caso de tener
problemas para instalar el paquete, puedes dirigirte a Carlos Vergara en
la dirección de correo <vergara_car@gva.es>: él te orientará acerca de
los pasos a seguir.
