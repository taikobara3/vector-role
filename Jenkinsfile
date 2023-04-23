pipeline {
    agent {
        label 'agent'
    }
    stages {
        stage('Checkout') {
            steps{
                git branch: 'master', credentialsId: 'd2860136-c0d9-4008-b96a-8ceea3e132cc', url: 'https://github.com/taikobara3/vector-role'
            }
        }
        stage('Install molecule') {
            steps{
                sh 'pip3 install -r test-requirements.txt'
                sh "echo =============="
            }
        }
        stage('Run Molecule'){
            steps{
                sh '/home/oleg/.local/bin/molecule test'
                // Clean workspace after testing
                cleanWs()
            }
        }
    }
}
