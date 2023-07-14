pipeline {
    agent any
    
    stages {
        stage('Check Ansible') {
            steps {
                script {
                    def ansible_exist = false
                    if (fileExists('/usr/bin/ansible')) {
                        ansible_exist = true
                    }
                    echo "Ansible exists: ${ansible_exist}"
                    
                    // You can perform further actions based on the ansible_exist variable
                    // For example, you can trigger different stages or steps depending on its value.
                    if (ansible_exist) {
                        echo "Skipping Ansible install -already exist"
                    } else {
                        // Perform actions when Ansible does not exist
                       sh 'sudo apt-add-repository ppa:ansible/ansible'
                       sh 'sudo apt install ansible'
                    }
                }
            }
        }
    }
}

