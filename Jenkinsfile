node {

def wspace = pwd()

    stage("Install Pre-requesites") {
        sh 'sudo apt-get install python-pip -y'
        sh 'sudo pip install --upgrade pip'
        sh 'sudo -H pip install virtualenv'
    }

    stage ("Get Latest Code") {
        checkout scm
    }

    stage("Install Python Virtual Enviroment") {
        sh 'virtualenv --no-site-packages .'
    }


    stage ("Install Application Dependencies") {
        dir(wspace) {
            sh 'sudo source ./bin/activate'
        }
    }
}   