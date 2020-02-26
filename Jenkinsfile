pipeline {
    agent any 
    stages {
           
        stage('Git Clone') { 
            steps {
                 echo 'Cloning...'
                //  git 'https://debashis.gopal:jivateam2@gitlab.jispl.com/Products/MagentoNAVPlatinum.git'
				   bat 'cd MagentoNAVPlatinum' 
				    bat 'git checkout dev'
            }
        }
        stage('submodule') { 
            steps {
					git 'submodule update --init --recursive'
                  git 'submodule foreach git pull origin dev'
                script {
                try{
                  bat 'mkdir ..\\app\\code'
                } catch(Exception e){
                  echo 'Exception occurred while removing old container...'
                }
                 
              }
            }
        }   
  
    }
}
