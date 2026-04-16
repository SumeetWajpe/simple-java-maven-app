pipeline{
    agent any

    environment {
        NEW_VERSION = '1.3.0'
        //SERVER_CREDENTIALS = credentials('sumeet-dockerhub')
    }

    tools{
        maven "jenkins-maven"
    }

    stages{
        stage("build"){
            
            steps{
                echo 'Building the application'
                echo "building version ${NEW_VERSION}"
                echo 'building version ${NEW_VERSION}'
                
                //sh 'mvn -B -DskipTests clean package'
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
                withCredentials([
                    usernamePassword(credentials: 'server-credentials', usernameVariable: USER,passwordVariable: PWD)
                ])

                sh "somescript ${USER} ${PWD} "
            }
        }
    }
    
}
