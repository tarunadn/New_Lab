pipeline {
    agent any 

    stages {
        stage('Build') { 
            steps { 
                cd /etc/ansible/
                sh 'sudo ansible all -m ping' 
            }
        }
        stage('Test'){
            steps {
                sh 'sudo ansible-playbook site.yml --syntax-check' 
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo ansible-playbook site.yml'
            }
        }
    }
}







#---
#- hosts: test1
#  become: yes
#  tasks:
#    - name: install epel-release
#     yum: name=epel-release state=latest
#    - name: install ansible
#      yum: name=ansible state=latest
#    - name: Install git
#      yum: name=git state=latest
#    - name: Install httpd service
#      yum: name=httpd state=latest
#    - name: ensure apache is running (and enable it at boot)
#      service: name=httpd state=started enabled=yes
#    - name: Install java service
#      yum: name=java state=latest
#    - name: Install Jenkins
#      yum: name=jenkins state=latest
#  handlers:
#    - name: restart httpd
#      service: name=httpd state=restarted
