pipeline {
    stages {
        stage('get code') {
            steps {
               dir('repo') {
                  checkout([$class: 'GitSCM', branches: [[name: "*/master"]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: "https://github.com/arcardon/simple-java-maven-app.git"]]])   
               sh "ls -atl"
               }
               sh "ls -alt"
            }
        }
    }
}
