pipeline {
    agent {
        label 'jenkins'
    }

    stages {
      // Install Apache2
        // stage('Install Apache2') {
        //     steps {
        //         script {         
        //             sh 'sudo apt-get update'
        //             sh 'sudo apt-get install -y apache2'
        //         }
        //     }
        // }

        // Start and enable Apache2 service
        stage('Start and Enable Apache2') {
            steps {
                script {
                    sh 'sudo systemctl start apache2'
                    sh 'sudo systemctl enable apache2'
                }
            }
        }

        // Move the folder to /var/www/html
        stage('Move Folder to /var/www/html') {
            steps {
                script {
                    sh 'sudo mv ./ /var/www/html/'
                }
            }
        }
    }
}
