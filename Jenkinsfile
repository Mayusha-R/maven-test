pipeline {
    agent any
    
    environment {
        MAVEN_HOME = tool 'Maven-3.9.0'
	    PATH = "$MAVEN_HOME/bin:$PATH"
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Building ...."
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
        	    sh "mvn test"   
            }
        }
    }
    post {
        success {
            echo 'Build and test succeeded!'
        }
        failure {
            echo 'Build or test failed!'
        }
    }
}