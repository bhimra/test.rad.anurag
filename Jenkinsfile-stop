pipeline {
    agent any
    
    stages {
        stage ('stop the services on release') {
            steps {
                sh '''
                    ssh -T root@192.168.60.175 << ENDSSH
                    systemctl stop raddc.service
                    systemctl stop radrtserver.service
                    systemctl stop radrema.service
                    systemctl stop rademagent.service
                    systemctl stop rademailserver.service
                    systemctl stop radchatclient.service
                    systemctl stop radchatagent.service
                    systemctl stop radrusc.service
                    systemctl stop radchatserver.service
                    systemctl stop radcrossx.service
                    systemctl stop radaes.service
                    systemctl stop radxspiservice.service
                    systemctl stop radccserver.service
                    systemctl stop radaws.service
                    systemctl stop radaws.service
                    echo -e '\n All the Server are stopped...................................................................'
ENDSSH
      '''
                }
            }
        }
    }
