#!/usr/bin/groovy
@Library('github.com/fabric8io/fabric8-pipeline-library@master') _

//mavenNode(mavenImage: 'openshiftio/launchpad-jenkins-slave') {
mavenNode {
  checkout scm

  stage("Build and Deploy") {
    container("maven") {
      sh "mvn help:effective-pom"
      sh "mvn -U clean fabric8:deploy -Popenshift -DskipTests"
    }
  }
}
