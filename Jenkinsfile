pipeline {
       agent any
            stages{
                 stage('Build-Deploy-Service'){
		when {
                	anyOf{
                    		branch "develop"; branch "main";
               			 }	
           		 }
                              steps{
                                sshagent(credentials:['b7b4b516-50ff-4318-875b-30e317231b8d']){
                                    sh '''#!/bin/bash
                                     ssh -t -o StrictHostKeyChecking=no root@193.176.241.175 ' cd /home/owncloud ; docker-compose stop '
                                     ssh -t -o StrictHostKeyChecking=no root@193.176.241.175 ' cd /home/owncloud ; docker-compose up -d --force-recreate '
                                    '''
                                }
                               echo "success "
                              }
                 }
         }
}
