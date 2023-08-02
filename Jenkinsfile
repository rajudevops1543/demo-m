pipeline {
    agent any 
    stages {
        stage('github-checkout') { 
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rajudevops1543/demo-m.git']])
            }
        }
        stage('mvn-build') { 
            steps {
                bat "mvn -f devops-1/pom.xml clean package"
            }
        }
        stage('Deploy') { 
            steps {
            bat "mvn -f devops-1/pom.xml clean tomcat7:deploy" 
            }
        }
    }
}
