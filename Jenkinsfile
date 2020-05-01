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
            }
        }
        stage('Release') {
            when { buildingTag() }
            options { 
                checkoutToSubdirectory('script')
            }
            steps {
                echo 'Releasing ASIC ${GIT_BRANCH} / ${TAG_NAME} / ${GIT_COMMIT}'
                git url: 'https://github.com/gjabouley-invn/subtreetest_child1.git',
                    branch: 'master',
                    poll: false
                bat '''
                dir
                set
                '''
            }
        }
    }
}
