pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
				sh 'mvn clean install'
				echo 'build success'
            }
		}
		stage('scan') {
            steps {
				sh 'mvn sonar:sonar -Dsonar.host.url=http://my58965dns.eastus2.cloudapp.azure.com:9000'
				echo 'scan success'
			}
        }
		stage('deploy') {
			steps {
				sh 'scp target/*.war http://my58965dns.eastus2.cloudapp.azure.com/apache-tomcat-8.5.35/webapps'
			}
		}
    }
}