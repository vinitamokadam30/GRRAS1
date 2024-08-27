pipeline{
    agent any
	triggers {
 	 pollSCM '* * * * *'
	}
	parameters {
  choice choices: ['DEV', 'QA', 'UAT'], name: 'ENVIORNMENT'
}
    stages{
        stage(checkout){
            steps{
                git 'https://github.com/vinitamokadam30/GRRAS1.git'
            }
        }
        stage(compilebuild){
        steps{
        sh 'mvn install'
        }
	}
	stage(compiledeploy){
        steps{
        sh 'cp target/GRRAS1.war /home/vinita/Documents/devops/apache-tomcat-9.0.93/webapps'
	if [ $ENVIRONMENT = "QA" ];then
	cp target/GRRAS1.war /home/vinita/Documents/devops/apache-tomcat-9.0.93/webapps
elseif  [ $ENVIRONMENT = "UAT" ];then
       cp target/GRRAS1.war /home/vinita/Documents/devops/apache-tomcat-9.0.93/webapps
echo "deployment has been done!"
fi
}
}
}
}


