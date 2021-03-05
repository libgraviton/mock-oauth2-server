#!groovy

node {

    stage('Checkout') {
        checkout scm
    }

    stage('Checkout & Bump') {
        grvDockerBuild(isJava: '13', addedArgs: '--group-add 998 -v /var/run/docker.sock:/var/run/docker.sock') {
            sh 'whoami'
            sh './gradlew jibDockerBuild --image="mock-auth2-server:develop" --debug'
        }
    }

}

