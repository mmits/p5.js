def REPO = 'https://github.com/mmits/p5.js'

pipeline{
	agent any
	
	stages{
		stage('Init'){
			steps{
				script{
					nodejs(nodeJSInstallationName: 'NodeJS'){
						git branch: 'main', url: REPO
    					dir('p5.js') {
							sh 'npm install'
    						sh 'npm test'
    					}
					}
				}
			}
		}
		
		stage('Linter'){
			steps{
				script{
					nodejs(nodeJSInstallationName: 'NodeJS'){
    					dir('p5.js') {
    						sh 'npm test'
    					}
					}
				}
			}
		}
	}
}

