pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
            	withMaven(mavenLocalRepo: "C:/Users/23824/.m2/repository/"){ bat 'mvn -B -DskipTests clean package' }
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            steps {
                bat 'C:/Users/23824/.jenkins/workspace/simple-java-maven-app/jenkins/scripts/deliver.sh'
            }
        }
    }
}