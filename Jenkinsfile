// pipeline {
//     agent {
//         docker {
//             image 'node:12' 
//             args '-p 3000:3000' 
//         }
//     }
//     environment {
//         CI = 'true'
//         HOME = '.'
//         npm_config_cache = 'npm-cache'
//     }
//     stages {
//         stage('Install Packages') { 
//             steps {
//                 sh 'npm install' 
//             }
//         }
//         stage('Test and Build') {
//             parallel {
//                 stage('Run Tests') {
//                     steps {
//                         sh 'npm run test'
//                     }
//                 }
//                 stage('Create Build Artifacts') {
//                     steps {
//                         sh 'npm run build'
//                     }
//                 }
//             }
//         }
//         stage('Production') {
//             steps {
//                 withAWS(region:'af-south-1',credentials:'cicd_creds') {
//                     s3Delete(bucket: 'cicd-jenkins-tutorial', path:'**/*')
//                     s3Upload(bucket: 'cicd-jenkins-tutorial', workingDir:'build', includePathPattern:'**/*');
//                 }
//             }
//         }
//     }
// }

pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
    }
}
