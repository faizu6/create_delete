pipeline {
    agent any
    stages {
        stage('build') {
            agent {
                docker { 
                    image 'faizu6/ansible-img1:17'
                    args "--user root --privileged"
                    
                }
            }
            steps {
                sh '''
                ansible-playbook main.yml -e name=${name} --tag ${tag}
                '''
            }
        }
    }
}
