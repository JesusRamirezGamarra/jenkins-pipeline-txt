pipeline{
    agent any

    triggers{
        githubPush() // Escuchgar cuando ocurra un evento push en el repositorio
    }

    stages{
        stage('Clonar repositorio'){
            steps{
                echo 'Clonando repositorio'
                git branch: 'develop', url: 'https://github.com/JesusRamirezGamarra/jenkins-pipeline-txt'
            }
        }

        stage('Listar estructura de proyecto'){
            steps{
                echo 'Listar estructura de proyecto'
                sh 'ls -R'
            }
        }

        stage('Visualizar archivo en especifico'){
            steps{
                script {
                    def archvoABuscar = "helloworld.txt"
                    if(fileExists(archvoABuscar)){
                        echo "El archivo ${archvoABuscar} existe"
                        sh "cat ${archvoABuscar}"
                    }
                    else{
                        echo "El archivo ${archvoABuscar} no existe"
                    }
                }
            }
        }

        stage('Compilar proyecto'){
            steps{
                echo 'Compilando proyecto'
                sh 'javac HelloWorld.java'
            }
        }
}