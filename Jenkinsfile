pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /home/osboxes/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }

        stage('Deliver') {
            steps {
                sh 'mvn spring-boot:run'
            }
        }        
    }

}
