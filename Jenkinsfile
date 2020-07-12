#!/usr/bin/env groovy

node (){

    stage 'Clean'
      deleteDir()

    stage 'Checkout'
    checkout scm

    stage 'Build Docker Image'

    sh "\$(aws ecr get-login)"
    def customimage = docker.build("my-image:${env.BUILD_ID}")
    customImage.push()

}