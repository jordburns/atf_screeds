node {

    stage("Install Pre-requesites") {
        sh 'sudo apt-get install python-pip -y'
        sh 'sudo pip install --upgrade pip'
        sh 'sudo -H pip install virtualenv'
    }

    stage ("Get Latest Code") {
        checkout scm
    }
    
    def installed = fileExists 'bin/activate'
    
    if (!installed) {
        stage("Install Python Virtual Enviroment") {
            sh 'virtualenv --no-site-packages .'
        }
    }  

    stage ("Install Application Dependencies") {
        sh '''
        . ${WORKSPACE}/bin/activate
        . ${WORKSPACE}/bin/pip freeze
        . ${WORKSPACE}/bin/pip install -r requirements.txt
        deactivate
        '''
    }
}   