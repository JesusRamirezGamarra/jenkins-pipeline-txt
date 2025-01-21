pipeline {
    agent any

    triggers {
        githubPush() // Escucha eventos de push en el repositorio
    }

    environment {
        RECIPIENT_EMAIL = 'luciojesusramirezgamarra@gmail.com' // Correo para notificaciones
    }

    stages {
        stage('Clonar repositorio') {
            steps {
                echo 'Clonando repositorio desde la rama lunes'
                git branch: 'lunes', url: 'https://github.com/JesusRamirezGamarra/pipeline-git-simple-rama-Lunes.git'
            }
        }

        stage('Listar estructura de proyecto') {
            steps {
                echo 'Listar estructura de proyecto'
                sh 'ls -R'
            }
        }

        stage('Ejecutar prueba simple') {
            steps {
                script {
                    echo 'Ejecutando prueba simple'
                    // Simulamos un proceso que puede fallar
                    sh '''
                    echo "Iniciando prueba simple..."
                    exit 1 # Simula un error
                    '''asdasd
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline ejecutado correctamente.'
        }
        failure {
            echo 'Error en el pipeline. Enviando notificación por correo...'
            mail to: "${RECIPIENT_EMAIL}",
                subject: "Error en el Pipeline: pipeline-git-simple-rama-Lunes",
                body: "Hubo un error durante la ejecución del pipeline en la rama 'lunes'. Por favor, revisa los registros en Jenkins."
        }
    }
}
