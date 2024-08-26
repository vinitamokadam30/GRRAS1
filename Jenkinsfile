pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/vinitamokadam30/GRRAS1.git'
            }
        }
        stage {
        stage('build')
        steps{
        sh 'mvn install'
        }
    }
        stage(deploy){
        steps{
        sh 'cp target/GRRAS1.war /home/vinita/Documents/devops/apache-tomcat-9.0.93/webapps'
}
}
}
}

