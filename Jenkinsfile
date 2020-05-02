pipeline {
    agent { label 'master' }
    stages {
        stage('Build') {
            steps {
                dir ('sources') { checkout scm }
                bat '''
                dir
                set
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Nothing to test yet'
                bat '''
                dir
                set
                '''
            }
        }
        stage('Release') {
            // when { buildingTag() }
            options { 
                checkoutToSubdirectory('script')
            }
            steps {
                dir ('scripts') { 
                    git url: 'https://github.com/gjabouley-invn/subtreetest_child1.git',
                        branch: 'master',
                        poll: false
                }
                echo "Releasing ASIC ${BRANCH_NAME} / ${GIT_COMMIT}"
                bat '''
                dir
                set
                '''
            }
        }
    }
}
