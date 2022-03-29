pipeline {
    agent any
    
    stages {
        stage ('stop the services on release') {
            steps {
                sh '''
                    ssh -T root@192.168.60.175 << ENDSSH
                    systemctl start raddc.service
                    systemctl start radrtserver.service
                    systemctl start radrema.service
                    systemctl start rademagent.service
                    systemctl start rademailserver.service
                    systemctl start radchatclient.service
                    systemctl start radchatagent.service
                    systemctl start radrusc.service
                    systemctl start radchatserver.service
                    systemctl start radcrossx.service
                    systemctl start radaes.service
                    systemctl start radxspiservice.service
                    systemctl start radccserver.service
                    systemctl start radaws.service
                    systemctl start radaws.service
                    echo -e '\n All the Server are stopped...................................................................'
ENDSSH
      '''
                }
            }
        }
    }
