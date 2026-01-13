
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/aryeshworks/DemoPerfTests.git'
            }
        }

        stage('Run Login Perf Test') {
            steps {
                bat '''
                cd jmeter
                jmeter -n ^
                  -t PracticeTestAutomation_Login_Test.jmx ^
                  -l results.jtl ^
                  -e -o report
                '''
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'jmeter/report/**', fingerprint: true
        }
    }
}
