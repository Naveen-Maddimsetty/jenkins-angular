pipeline {
     agent any
     stages {
        stage("Install Dependencies") {
            steps {
                sh "sudo npm install -g @angular/cli"
                sh "sudo npm install"
            }
        }

        stage("Build") {
            steps {
                sh "sudo ng build"
            }
        }

        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/dist"
                sh "sudo cp -r ${WORKSPACE}/dist/ /var/www/dist/"
            }
        }
    }
}
