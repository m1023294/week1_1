pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
				sh 'mvn clean install'
				sh 'mvn sonar:sonar -Dsonar.host.url=http://my58965dns.eastus2.cloudapp.azure.com:9000'
				echo 'here I am'
            }
        }
    }
}