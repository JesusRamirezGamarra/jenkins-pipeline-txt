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
                    def archivoABuscar = "helloworld.txt" // Corrige el nombre de la variable
                    if(fileExists(archivoABuscar)){
                        echo "El archivo ${archivoABuscar} existe"
                        sh "cat ${archivoABuscar}"
                    }
                    else{
                        echo "El archivo ${archivoABuscar} no existe"
                    }
                }
            }
        }

        stage('Compilar proyecto'){
            steps{
                echo 'Compilando proyecto'
            }
        }
    }
}