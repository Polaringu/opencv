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
        
        stage('Run Core Tests') {

			steps {
				sh """
        cd build
        cd bin
        cd Release
        opencv_test_core.exe --gtest_filter=-*Core_InputOutput.filestorage_base64_basic_*:*Core_globbing.accuracy*
        """
			}
		}
	}
}
