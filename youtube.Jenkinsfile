pipeline {
    agent any

    parameters {
        string(name: 'BRANCH', defaultValue: 'Master', description: 'Branch name')
    }

    stages {
        stage('Step1') {         
            steps {
                echo 'step 1'
                sh 'printenv'
            }
        }
        stage('Step2') {
            when {
                expression { BRANCH ==~ /(Master|Hotfix)/}
            }
            steps {
                echo 'step 2'
            }
        }
        stage('Step3') {
            when {
                expression { BRANCH ==~ /(Release)/}
            }            
            steps {
                echo 'step 3'
            }
        }
    }
}