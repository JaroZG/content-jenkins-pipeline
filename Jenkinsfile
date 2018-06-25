pipeline {
	options {
    		buildDiscarder(logRotator(numToKeepStr: '2', artifactNumToKeepStr: '1'))
  		}
	
	agent any
		stages {
		stage('build') {
			steps {
				sh 'javac -d . src/*.java'
				sh 'echo Main-Class: Rectangulator > MANIFEST.MF'
				sh 'jar -cvmf MANIFEST.MF rectangle.jar *.class'
				}
				}
			}
		post {
			success {
		archiveArtifacts artifacts: 'rectangle.jar', fingerprint:true
				}
			}


	}

