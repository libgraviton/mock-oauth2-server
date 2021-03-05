#!groovy

node {

    stage('Checkout') {
        checkout scm
    }

    stage('Checkout & Bump') {
        sh './gradlew jibDockerBuild --image="grv/mock-oauth2-server:develop"'

        grvDockerBuild.dockerBuild() {
            image = docker.image('grv/mock-oauth2-server:develop')
            image.push('develop')
        }
    }

}

