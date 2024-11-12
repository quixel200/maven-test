pipeline{
    agent any
        tools{
            maven 'maven'
        }

    stages{
        stage('Checkout'){
            steps{
                checkout scm
            }
        }
        stage('Build'){
            steps{
                dir('quixel'){
                    sh 'mvn clean install'
                }
            }
        }

        stage('Deploy'){
            steps{
                sh 'cp target/*.war /tmp'
            }
        }
    }
    post{
        success {
            echo "success!"
        }
        failure{
            echo "failed!"
        }
    }
}
