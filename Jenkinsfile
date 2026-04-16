pipeline{
    agent any

    tools{
        maven "jenkins-maven"
    }

    stages{
        stage("build"){
            steps{
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage("test"){
            steps{
                echo "testing the application"
                //sh 'mvn -B -DskipTests clean package'
            }
        }
        stage("deploy"){
            steps{
                echo "deploying the application"
            }
        }
    }
    
}
