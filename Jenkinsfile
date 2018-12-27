#!/usr/bin/env groovy

node {
    stage('checkout') {
        checkout scm
    }

    stage('check java') {
        sh "java -version"
    }

    stage('clean') {
        sh "chmod +x mvnw"
        sh "./mvnw clean"
    }

//    stage('Prepare') {
//        withEnv(['MYTOOL_HOME=/home/qk/.nvm/versions/node/v8.9.4/bin']) {
//            sh '$MYTOOL_HOME/npm install -g yarn'
//        }
//    }

//    stage('install tools') {
//        sh "./mvnw com.github.eirslett:frontend-maven-plugin:install-node-and-yarn -DnodeVersion=v8.9.4 -DyarnVersion=v1.12.3"
//    }

//    stage('yarn install') {
//        sh "./mvnw com.github.eirslett:frontend-maven-plugin:yarn"
//    }

//        stage('npm install') {
//        sh "./mvnw com.github.eirslett:frontend-maven-plugin:npm"
//    }


//    stage('backend tests') {
//        try {
//            sh "./mvnw test"
//        } catch(err) {
//            throw err
//        } finally {
//            junit '**/target/surefire-reports/TEST-*.xml'
//        }
//    }

//    stage('frontend tests') {
//        try {
//            sh "./mvnw com.github.eirslett:frontend-maven-plugin:yarn -Dfrontend.yarn.arguments=test"
//        } catch(err) {
//            throw err
//        } finally {
//            junit '**/target/test-results/karma/TESTS-*.xml'
//        }
//    }

//    stage('package and deploy') {
//        sh "./mvnw com.heroku.sdk:heroku-maven-plugin:1.1.1:deploy -DskipTests -Pprod -Dheroku.appName="
//        archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
//    }

    stage('package') {
        sh "./mvnw package -DskipTests -Dhttps.protocols=TLSv1.2 -Pprod"
//        archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
    }


}
