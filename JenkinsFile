pipeline {
    agent any
    stages {
        
        stage('Get Input') {
            steps {
                sh 'echo "Get Input" '
            }
        }
        
        stage('Test Connectivity') {
            steps {
                sh 'echo "Test Connectivity" '
            }
        }
        
        stage('Check config') {
            steps {
                sh 'echo "Check config" '
            }
        }
        
       
        
        stage('Copy from D2CCM') {
            steps {
                //Copy data from source
                sh 'cp -f /home/pushpak/Delivery/${DELIVERY_ID}/${TAR_FILE} . '
            }
        }
        
        stage('Backup') {
            steps {
                sh 'echo "Backup" '
            }
        }
        
        stage('Deploy') {
            steps {
                //Untarring compressed file
                sh 'tar -xvf ${TAR_FILE}'
            }
        }
        stage('post') {
            steps {
                //Create log file
                sh 'ls -lrt'
                sh 'touch ${DELIVERY_ID}.log.txt'
                
                //Add Run time in log'
                sh 'date >> ${DELIVERY_ID}.log.txt'
                
                //Remove tar and adding in log file
                sh 'echo "Removing ${TAR_FILE}" >> ${DELIVERY_ID}.log.txt'
                sh 'rm ${TAR_FILE}'
                sh 'ls -lrt'
            }
        }
    }
}
