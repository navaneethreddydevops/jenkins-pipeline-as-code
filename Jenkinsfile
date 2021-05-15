#!/usr/bin/env groovy
pipeline {
    options {
        timestamps()
    }
    stages {
        stage('Maven Build') {
            steps {
                sh 'mvn --no-transfer-progress -B clean test'
            }
            post {
                always {
                    junit(keepLongStdio: true, testResults: 'target/surefire-reports/TEST-*.xml')
                }
            }
        }
    }
}
