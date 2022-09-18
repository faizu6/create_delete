pipeline {
    agent any
    parameters {
        string(name: 'Project', defaultValue: 'dog', description: 'what is the name of the department for which task is needed?')
        choice(name: 'tag', choices: ['Run', 'Stop'], description: 'Choose whether to create or delete')
        }
    environment { 
        project = "${params.Project}"
        tag = "${params.tag}"
    }
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
                ansible-playbook main.yml -e name=$Project --tag $tag
                '''
            }
        }
    }
}
