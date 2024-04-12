pipeline {
    agent {
        label 'ansible'
    }
    
    environment {
        PYENV_ROOT = "/usr/local/pyenv"
        PATH = "${PYENV_ROOT}/bin:/usr/local/bin:${PATH}"
    }

    stages {
        stage('Build') {
            steps {
                // Получить код из репозитория GitHub
                git branch: 'jenkins', url: 'https://github.com/ivvklimov/ansible-role-vector.git'
            }
        }
        
        stage('Molecule test') {
            steps {
                script {
                   sh '''
                        eval "$(pyenv init --path)"
                        molecule test -s default
                    '''
                }
            }
        }
    }
}
