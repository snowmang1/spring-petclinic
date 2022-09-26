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
		"172.17.0.2:8081/artifactory/webapp/#/admin/repository/local/spring-clinic" \
		-T target/spring-petclinic-2.7.0-SNAPSHOT.jar'
            }
        }
    }
}
