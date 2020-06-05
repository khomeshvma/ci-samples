pipeline {
  agent {
    node { label 'katalon' }
 }

    stages {
        stage('Test') {
            steps {
                sh 'katalonc.sh -browserType="Chrome" -retry=0 -statusDelay=15 -testSuitePath="Test Suites/TS_RegressionTest"'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'report/**/*.*', fingerprint: true
            junit 'report/**/JUnit_Report.xml'
        }
    }
}
