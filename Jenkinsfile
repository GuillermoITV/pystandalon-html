pipeline {
    agent {
        label 'agente1'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'pip install -r requirements_dev.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'tox -e py'
            }   
        }
        stage('deploy') {
            steps {
                sh 'python3 setup.py sdist bdist_wheel'
            }   
        }        
    }
}
