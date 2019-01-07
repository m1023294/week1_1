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
			steps{
				sshagent (['tomcat']){
					sh 'scp target/*.war /apache-tomcat-8.5.35/webapps'
					echo 'deployed'
				}
			}
		}
    }
}