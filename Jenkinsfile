pipeline{
    agent any
    
    stages {
        stage ('Checkout SCM') {
            steps {
                
                sh '''
                  git 'https://github.com/bhimra/test.rad.anurag.git'
                  pwd && chmod +x .
                '''
            }    
        }
    stage {
        steps {
            sh '''
                ssh -T centos@192.168.60.175 << ENDSSH
                cd 
                systemctl start oodb.service
                systemctl start radaws.service
                systemctl start radccserver.service
ENDSSH
      '''
            }
        }
    stage ('start the Ct-Client'){
        input {
            message "Did you start the ct-client?"
        }
        steps {
            sh '''
                ssh -T centos@192.168.60.175 << ENDSSH
                cd 
                systemctl start radxspiservice.service
                systemctl start radaes.service
                systemctl start radcrossx.service
                sleep 5
                systemctl start radchatserver.service
                systemctl start radrusc.service
                systemctl start radchatagent.service
                systemctl start radchatclient.service
                sleep 5
                systemctl start rademailserver.service
                systemctl start rademagent.service
                systemctl start radrema.service
                sleep 5
                systemctl start radrtserver.service
                systemctl start raddc.service
                echo "\n all the servers are running......"
ENDSSH
      '''
            }
        }
    }
}
