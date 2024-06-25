pipeline {
    agent any

    environment {
        // Set application name and version
        APP_NAME = 'py_app'
        VERSION = '1.0.0' // Set your app version
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Dineshkundo/Build-python-using-jenkins-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'python3 ops.py'
            }
        }

        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }

        stage('Package Application') {
            steps {
                script {
                    // Package the application
                    sh "tar -czf ${APP_NAME}-${env.BUILD_NUMBER}-${VERSION}.tar.gz *"
                }
            }
        }
    }
}

// pipeline {
//     agent any

//     stages {
//         stage('Checkout') {
//             steps {
//                 checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Dineshkundo/Build-python-using-jenkins-pipeline.git']]])
//             }
//         }
//         stage('Build') {
//             steps {
//                 git branch: 'main', url: 'https://github.com/Dineshkundo/Build-python-using-jenkins-pipeline.git'
//                 sh 'python3 ops.py'
//             }
//         }
//         stage('Test') {
//             steps {
//                 sh 'python3 -m pytest'
//             }
//         }
//          stage('Package Application') {
//             steps {
//                 // Package the application
//                 sh 'tar -czf ${APP_NAME}-${BUILD_NUMBER}-${VERSION}.tar.gz *'
//             }
//         }
//     }
// }
