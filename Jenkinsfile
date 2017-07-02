node {
    def installed = fileExists 'bin/activate'

    if (!installed) {
        stage("Install Pre-requesites") {
            sh 'sudo apt-get install python-pip -y'
            sh 'sudo pip install --upgrade pip'
            sh 'sudo -H pip install virtualenv'
       }
        stage("Install Python Virtual Enviroment") {
            sh 'virtualenv --no-site-packages .'
        }
    }   
}
