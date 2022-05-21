pipeline {
	
	agent any

	stages {

		stage ('Clean') {
			steps {
				sh "git clean -fdx"
			}
		}

		stage('Build') {

			steps {
				sh """
        mkdir build
        cd build
        cmake ..
        cmake --build . --config Release
        """
			}
		}
	}
}
