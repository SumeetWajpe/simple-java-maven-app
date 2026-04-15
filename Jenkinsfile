pipeline{
    agent any

    tools{
        maven "jenkins-maven"
    }

    stages{
        stage("Build"){
            steps{
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
