pipeline {
    agent any
    stages {
        stage('SonarQube Quality Gate') {
            environment {
                scannerHome = tool 'Sonar-qube'
            }
            steps {
                withSonarQubeEnv('sonar-qube') {
                    sh "${scannerHome}/bin/sonar-scanner"
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

