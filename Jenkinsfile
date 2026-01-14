
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/aryeshworks/DemoPerfTests.git'
            }
        }

        stage('Run Login Perf Test') {
            steps {
                bat '''
                cd jmeter

                if exist report rmdir /s /q report
                if exist results.jtl del /f /q results.jtl

                jmeter -n ^
                  -t PracticeTestAutomation_Login_Test.jmx ^
                  -l results.jtl ^
                  -e -o report
                '''
            }
        }

        stage('Run Interview Ops Perf Test') {
            steps {
                bat '''
                cd jmeter

                if exist interviewOpsReport rmdir /s /q interviewOpsReport
                if exist interviewOps.jtl del /f /q interviewOps.jtl
                
                jmeter -n ^
                  -t PracticeTestAutomation_InterviewOps_Test.jmx ^
                  -l interviewOps.jtl ^
                  -e -o interviewOpsReport
                '''
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'jmeter/report/**, jmeter/interviewOpsReport/**', fingerprint: true
        }
    }
}
