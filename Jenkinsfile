pipeline {
    agent any
    tools {
      maven 3.9.9
    }
    stages {
//        stage('get code') {
//            steps {
//               dir('repo') {
//                  checkout([$class: 'GitSCM', branches: [[name: "*/master"]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: "https://github.com/arcardon/simple-java-maven-app.git"]]])   
//               sh "a=`ls`"
//               sh "echo $a"
//               sh "ls "
//               }
//               sh "ls "
//            }
//        }
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
            }
        }
    }
}
