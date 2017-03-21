# Integrar Heroku con GitHub
Para poder integrar de una forma fácil y rápida los proyectos de GitHub
con Heroku hay que seguir los siguientes pasos:
1. Primero hay que crearse una cuenta gratuita en [Heroku](https://signup.heroku.com/dc).
A continuación, hay que seleccionar el lenguaje de desarrollo principal, aunque 
posteriormente no influye para nada.
1. Una vez creada la cuenta, hay que acceder al [Dashboard](https://dashboard.heroku.com/apps) 
de tu cuenta y crear una aplicación nueva (menú desplegable "New" de arriba a la 
derecha). A continuación hay que introducir un nombre para la aplicación (se puede 
dejar en blanco y se asignará uno automático) y escoger el servidor en el que deseas desplegar.
1. Se ha de acceder a la aplicación recién creada, a la sección de "Deploy". En el 
apartado de "Deployment method" hay que seleccionar sincronizar con GitHub.
Ahora, se ha de introducir el nombre del repositorio de GitHub con el cual se desea
sincronizar el despliegue y darle al botón de "Connect".
1. Una vez se ha completado satisfactoriamente el paso anterior, aparecerán dos nuevas
secciones, "Automatic deploys" y "Manual deploys":
   1. **Automatic deploys:** Suele ser la forma más comoda de desplegar las aplicaciones.
   Esto permite que con cada commit o push que se haga en la rama seleccionda 
   del repositorio de GitHub, se inicie automáticamente un proceso de despliegue. 
   Para ello, hay que seleccionar la rama del repositorio con la que se quiere 
   desplegar y elegir si se desea que antes de cada despliegue, se compruebe si 
   ha pasado el sistema de CI. Por último hay que darle al botón de "Enable Automatic Deploys".
   1. **Manual deploys:** Este tipo de despliegue permite que únicamente se haga el despliegue
   de la aplicación cuando se haga click en el botón de "Deploy branch".
1. Una vez finalizado el paso anterior, ya debería de estar desplegada la aplicación.
Para comprobarlo, hay que hacer click en el botón de arriba a la derecha "Open app",
el cual te abrirá automáticamente en el navegador la aplicación desplegada.
1. Si algo ha ido mal en el despliegue de la aplicación, o en algún momento durante 
el ciclo de vida de la misma, se puede acceder al menú desplegable de arriba a la 
derecha "More", y seleccionar "View logs".