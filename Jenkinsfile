pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = "False"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Prasanth-sys/gjfiles.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh '''
                    echo "Running Ansible..."
                    ansible-playbook -i inventory/hosts playbooks/web.yml
                '''
            }
        }

        stage('Validate Deployment') {
            steps {
                script {
<<<<<<< HEAD
                    // Replace EC2_PUBLIC_IP
=======
>>>>>>> 555e9031afc0e02b3826a9ba40df25f10f345b43
                    def output = sh(script: "curl -s http://44.200.188.54", returnStdout: true).trim()

                    if (!output.contains("Harika")) {
                        error("Webserver validation failed!")
                    }
                }
            }
        }
    }

    post {
        success {
            echo "Deployment Successful!"
        }
        failure {
            echo "Deployment Failed!"
        }
        always {
            echo "Pipeline Finished!"
        }
    }
}
