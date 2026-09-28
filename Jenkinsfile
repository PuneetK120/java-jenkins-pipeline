pipeline {
    agent { label 'j_env'}
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean compile'
                sh 'sleep 5'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -cp target/classes HelloWorld'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
    }
}
