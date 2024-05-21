# Jenkins Example 2. Pipeline Job

## Pipeline

- Crea un Tarea de Pipeline

- En Pipeline, elige Pipeline Script e introduce el siguiente código:

```
pipeline {

    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
           }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
```

En el enlace Pipeline Syntax puedes acceder a un generador de código que te puede ayudar a completar la sistaxis de la pipeline.

- Pulsa en Guardar

- Ejecuta la tarea y comrpueba el resultado. Navega por las diferentes opciones de la ejecución.

## Jenkinsfile

Crea el fichero Jenkinsfile con el contenido anterior, crea un repositorio en Github y sube este fichero. 

Modifica la tarea para que utilice el repositorio git, obtenga la pipeline de este fichero Jenkinsfile y se ejecute cada vez que hagas un push en el repositorio.

Para ello:

- En "Configurar el origen del código fuente": Repositorio Git

- En "Disparadores de ejecuciones": GitHub hook trigger for GITScm polling.
NOTA: Es necesario añadir un WebHook a este repositorio de Github, con URL http://<jenkins_server>/github-webhook/, par que se ejecute con cada PUSH.

- En Pipeline, elige Pipeline Script fron SCM; en Repository URL incluye la URL del repositorio; no son necesarias credenciales si en un repositorio público; en Branch escribe el nombre de la rama y en Script Path indica la ruta al fichero Jenkinsfile.

Ahora, cada vez que subamos una nueva versión a nuestro repositorio Github se activará la tarea y se ejecutará la Pipeline tal como se describa en el fichero Jenkinsfile. 





