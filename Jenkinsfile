pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                withMaven(mavenLocalRepo: ".repository"){ bat 'mvn -B -DskipTests clean package' }
        	//stash includes: ".repository/", name "repository"
                //cmd 'mvn -B -DskipTests clean package' 
            }
        }
    }
}