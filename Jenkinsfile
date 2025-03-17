pipeline{ 
    agent any
    environment{ 
        ansible_name = vagrant
        ansible_node = 192.168.56.15
    }

    stages{ 
        stage('Copy folder to the ansible node'){ 
            script{ 
                sh " scp -r templatemo_591_villa_agency ${ansible_name}@${ansible_node}:/home/vagrant/files/"
            }
        }
        stage("Running the anisble playbook "){ 
            script{
                sh " ssh ${ansible_name}@${ansible_node} 'ansible-playbook -i /home/vagrant/ansible/inventory.ini /home/vagrant/anisble/deploy.yml'"
            }
        }
    }
}
