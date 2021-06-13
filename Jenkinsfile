#!groovy

pipeline {
    environment {
        JAVA_TOOL_OPTIONS = "-Duser.home=/var/maven"
    }
    agent {
        any {
            image "maven:3.6.3-jdk-8-alpine"
            label "docker"
            args "-v /tmp/maven:/var/maven/.m2 -e MAVEN_CONFIG=/var/maven/.m2"
        }
    }

    stages {
      stage("test") {
            steps {
                sh "./mvnw -version"
            }
        }
        stage("Build") {
            steps {
                sh "mvn -version"
                sh "./mvnw -version"
                sh "mvn clean install"
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}