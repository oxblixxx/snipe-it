pipeline {
    agent any
    stages {
        stage('SonarQube Quality Gate') {
            environment {
                scannerHome = tool 'snipe-it'
            }
            steps {
                withSonarQubeEnv('snipe-it') {
                    sh "${scannerHome}/bin/sonar-scanner"
                    // sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}



//     // stage('Scan') {
//     //   steps {
//     //     withSonarQubeEnv(installationName: 'sonar-qube') { 
//     //       sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
//     //     }
//       }
//     }
//   }
// }

