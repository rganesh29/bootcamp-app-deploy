pipeline {
    agent {
        label 'jenkins'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // Update package list and install required packages
                    sh 'sudo apt-get update'
                    sh 'sudo apt-get install -y apache2 unzip'
                }
            }
        }

        stage('Unzip Avocado.zip') {
            steps {
                script {
                    // Unzip Carvilla.zip
                    sh 'sudo unzip Carvilla.zip -d ./Carvilla'
                }
            }
        }

        stage('remove apache2 index.html file and empty folder') {
            steps {
                script {
                    // remove apache2 index.html file and empty folder
                    sh 'sudo rm -r *'
                }
            }
        }

        stage('Move Folder to /var/www/html') {
            steps {
                script {
                    // Move the folder to /var/www/html
                    sh 'sudo mv ./Carvilla/carvilla-v1.0/* /var/www/html/'
                }
            }
        }

        stage('Start and Enable Apache2') {
            steps {
                script {
                    // Start and enable Apache2 service
                    sh 'sudo systemctl start apache2'
                    sh 'sudo systemctl enable apache2'
                }
            }
        }
    }
}
