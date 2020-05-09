node {
  
  stage('Checkout Source Code') {
    checkout scm
  }

  stage('Create Docker Image') {
    docker.build("docker_image:5")
  }

  stage ('Run Application') {
    try {
      // Stop existing Container
      sh 'docker rm docker_container -f'
      // Start database container here
      
    } 
	catch (error) {
    } finally {
      // Stop and remove database container here
      
    }
  }
  
  stage ('Notifications') {
    mail body: "Project Execution Completed with status : " + currentBuild.result ,
                     subject: 'Project Execution Notification',
                     to: 'abc@abc.com'
     }
 }
