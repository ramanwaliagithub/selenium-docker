// pipeline {
//     // master executor should be set to 0
//     agent any
//     stages {
//         stage('Build Jar') {
//             steps {
//                 sh "mvn clean package -DskipTests"
//             }
//         }
//         stage('Build Image') {
//             steps {
//                 sh "docker build -t='ramandocker009/selenium-docker' ."
//             }
//         }
//         stage('Push Image') {
//             steps {
// 			    withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'pass', usernameVariable: 'user')]) {
// 			        sh "docker login --username=${user} --password=${pass}"
// 			        sh "docker push ramandocker009/selenium-docker:latest"
// 			    }                           
//             }
//         }
//     }
// }

pipeline {
    // master executor should be set to 0
    agent any
    stages {
        stage('Build Jar') {
            steps {
                bat "mvn clean package -DskipTests"
            }
        }
        stage('Build Image') {
            steps {
                bat "docker build -t='ramandocker009/selenium-docker' ."
            }
        }
        stage('Push Image') {
            steps {
			    withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'pass', usernameVariable: 'user')]) {
			        bat "docker login --username=${user} --password=${pass}"
			        bat "docker push ramandocker009/selenium-docker:latest"
			    }                           
            }
        }
    }
}



