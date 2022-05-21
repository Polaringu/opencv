pipeline {
	
	agent any

	stages {

		stage ('Clean') {
			steps {
				sh "git clean -fdx"
			}
		}

		stage('Make') {

			steps {
				sh """
        mkdir build
        cd build
        cmake ..
        """
			}
		}
        
        stage('Build') {

			steps {
				sh """
        cd build
        cmake --build . --config Release
        """
			}
		}
	}
}
