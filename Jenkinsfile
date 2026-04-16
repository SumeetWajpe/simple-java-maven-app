pipeline{
    agent any

    parameters{
        choice(name: 'VERSION', choices:['1.1.0','1.2.0','1.3.0'],description:'')
        booleanParam(name: 'executeTests', defaultValue: true, description:'')              
    }

    
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
            when {
                expression{
                    params.executeTests
                }
            }
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
