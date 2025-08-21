pipeline {
    agent any

    stages {
        stage('Clone Git Repository') {
            steps {
                git branch: 'main',
                    credentialsId: 'ansible-ssh',
                    url: 'git@github.com:Sathya252/jenkins-ansible.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'addressbook.yml',        // your playbook file
                    inventory: 'inventory.ini',         // your inventory file
                    credentialsId: 'ansible-ssh',      // SSH credentials for nodes
                    colorized: true,
                    disableHostKeyChecking: true,
                    installation: 'ansible2'           // name of Ansible installation in Jenkins Global Tool Config
                )
            }
        }
    }
}
