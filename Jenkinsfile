pipeline{

    agent any

    stages{

        stage("C. Download"){

            steps{
                git branch: 'main', url: 'https://github.com/clemenrance/DEV-TEAM.git'
            }
        }
        stage("Unit Test"){

            steps{
                sh 'mvn test'
            }
        }
        stage("Integration Test"){

            steps{
                sh'mvn verify -DskipUnitTests'
            }
        }
        stage("C. Build"){

            steps{
                sh'mvn clean install'
            }
        }
        stage("Static Test"){

            steps{

                script{
                    withSonarQubeEnv(credentialsId: 'Sonar-auth'){
                       sh 'mvn clean package sonar:sonar' 
                    }
                }
            }
        }

    }

}