pipeline {
    agent any

    // triggers{
    //     bitbucketPush()
    // }

    stages {
        stage ('Test & Build Artifact') {
            agent {
                docker {
                    image 'openjdk:11'
                    args '-v "$PWD":/app'
                    reuseNode true
                }
            }
            steps {
                sh "chmod +x gradlew"
                // sh './gradlew  build --no-daemon'
                sh './gradlew build'
                sh './gradlew test'
                sh './gradlew run'
                
            }
        }
        
        
    }
}