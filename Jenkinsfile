def dockeruser = "40404040"
def imagename = "wordpress-with-java:5.4.1"
def container = "apache2"
node {
   echo 'Building Apache Docker Image'

stage('Git Checkout') {
    git 'https://github.com/jvpreis/ESII'
    }
    
stage('Build Docker Image'){
     powershell "docker build -t  ${imagename} ."
    }
    
stage('Stop Existing Container'){
     powershell "docker stop ${container}"
    }
    
stage('Remove Existing Container'){
     powershell "docker rm ${container}"
    }
    
stage ('Runing Container to test built Docker Image'){
    powershell "docker run -dit --name ${container} -p 80:80 ${imagename}"
    }
    


}
