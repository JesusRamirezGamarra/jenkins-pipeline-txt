pipeline{
    agent any

    triggers{
        githubpush() // Escuchgar cuando ocurra un evento push en el repositorio
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
    }
}