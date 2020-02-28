pipeline {
    agent any
    environment {
        GIT_HASH = GIT_COMMIT.take(7)
        Version_Major = '1'
        Version_Minor  = '0'
        Version_Patch  = '0'
        VERSION = VersionNumber([
        versionNumberString : "${Version_Major}.${Version_Minor}.${BUILD_NUMBER}-${GIT_HASH}",
        projectStartDate : '2020-01-01',
        versionPrefix : 'v.'
        ])
   }

    stages {
        stage ('Get Version') {
            steps {
                sh 'echo "$VERSION"';
            }
        }
        stage ('checkout') {
            steps {
                dir( "$VERSION" ) {
                    checkout changelog: false, poll: false, scm: [$class: 'GitSCM',
                             branches: [[name: '*/jenkins']],
                             doGenerateSubmoduleConfigurations: false,
                             extensions: [],
                             submoduleCfg: [],
                             userRemoteConfigs: [[credentialsId: '', url: 'git@github.com:SergeyVolynkin/scalyr-frontend.git']]]
                }
            }
        }
        stage ('Install dependencies') {
            steps {
                sh """
                    virtualenv -p python3 venv
                    . venv/bin/activate
                    yarn install --frozen-lockfile
                """
            }
        }
        stage ('Test & Build') {
            steps {
                sh """
                    yarn test --watchAll=false
                    yarn run react-scripts build
                """
            }
        }
    }
}