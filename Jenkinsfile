pipeline {  

    agent any

    stages {
        stage('clone python assignment repo') {
            steps {
                git branch: 'master',
                url: 'https://github.com/harshithakishor/python_assignment.git'
            }
        }
        stage ('install dependencies') {
            steps {
                sh ''' 
                #apt list --installed  | grep python3-pip || apt-get install python3-pip
				pip3 install -r requirement.txt
                '''
            }
        }
		stage ('run testCases') {
            steps {
                sh ''' 
                python3 -m pytest
                '''
            }
        }
        stage("docker build") {
            steps {
                sh "echo 'build the image'" 
            }
        }
        stage("docker push command") {
            steps {
			    sh '''
				  echo "pushing the image"
				'''
            }
        }
	}
		
}
