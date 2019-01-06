pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
				sh 'mvn clean install'
				echo 'build success'
            }
		}
		stage('deploy') {
			sshagent (['05644746-d63a-46a6-96bf-72a456f2b234']){
			steps {
				sh 'scp target/*.war http://my58965dns.eastus2.cloudapp.azure.com/apache-tomcat-8.5.35/webapps'
				echo 'deployed'
			}
			}
		}
    }
}