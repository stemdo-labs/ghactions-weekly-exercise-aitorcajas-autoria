He pensado que la mejor forma de hacer el ejercicio es crear un trigger principal para cuando se haga push en main o en development, este workflow tiene 3 jobs:
- Un job que define en un output el entorno mediante un reusable.
- Otro que llama a un reusable que ejecuta el CI, si el entorno es UAT solo ejecuta el CI, si es producción ejecuta los tests y luego el CI. Para ejecutar el CI llamo a un action que devuelve el nombre de la imagen que se creará tageado, el cual es guardado en un output.
- Y por último otro que mediante el nombre de la imagen y el nombre del entorno despliega el CD.

En cuanto a los aprobadores de entorno me he puesto a mí en los dos y como variables y secretos he declarado el usuario y la contraseña de DockerHub.
