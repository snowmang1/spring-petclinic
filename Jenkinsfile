pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh './mvnw package'
            }
        }
        stage('Test') {
            steps {
                echo './mvnw test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'curl -u admin:Password -X PUT \
		"172.17.0.3:8081/artifactory/libs-release/spring-petclinic-2.7.0.jar" \
		-T "/home/alpuser/.jenkins/workspace/jenkins-pipeline_main/target/spring-petclinic-2.7.0.jar"
            }
        }
    }
}
