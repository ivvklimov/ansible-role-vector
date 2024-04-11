pipeline {
    agent {
        label 'ansible'
    }
    stages {
        stage('First') {
            steps {
                // sh 'ansible-playbook --version'
                sh 'uptime'
            }
        }
        stage('Second') {
            steps {
                sh 'echo Hello'
                sh 'echo "second step"'
            }
        }
    }
}
