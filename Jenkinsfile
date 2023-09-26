pipeline {
    agent any 
    tools {
         maven 'maven'
         jdk 'java'
    }
    stages {
       stage('Stage-0 : Static Code Analysis Using SonarQube') { 
           steps {
                sh 'mvn clean verify sonar:sonar'
            }
        }

        stage('Stage-1 : Clean') { 
            steps {
                sh 'mvn clean'
            }
        }
         stage('Stage-2 : Validate') { 
            steps {
                sh 'mvn validate'
            }
        }
         stage('Stage-3 : Compile') { 
            steps {
                sh 'mvn compile'
            }
        }
         stage('Stage-4 : Test') { 
            steps {
                sh 'mvn test'
            }
        }
          
          stage('Stage-5 : Verify') { 
            steps {
                sh 'mvn verify'
            }
        }
          stage('Stage-6 : Package') { 
            steps {
                sh 'mvn package'
            }
        }
          stage('Stage-7 : Install') { 
            steps {
                sh 'mvn install'
            }
        }
        stage('Stage-8 : Deploy an Artifact to Artifactory Manager i.e. Nexus/Jfrog') { 
            steps {
                sh 'mvn deploy'
            }
        }
    }
}
