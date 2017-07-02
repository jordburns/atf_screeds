node {

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
    wspace = "/var/lib/jenkins/workspace/atf_pipeline/"
    ws(wspace) {
        sh '''
            source bin/activate
            pip install -r requirements.txt
            deactivate
           '''
        }
    }
}   