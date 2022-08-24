pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven3.8.4"
    }

    stages {
        stage('checkout') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/adesinaabibat/hello-world.git'

            }
        }
        
        stage('build') {
            steps {
                // This is to build the job
                 sh "mvn clean package"

            }
        }
        stage('imagetag') {
            steps {
                // This is to tag the job
                 
                 sh "docker build -t ab4ever/hello-world:${BUILD_NUMBER} ." 
                 sh "docker push a4ever/hello-world:$BUILD_NUMBER"
    }
        }
    }
}
