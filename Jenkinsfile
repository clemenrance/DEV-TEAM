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

    }

}