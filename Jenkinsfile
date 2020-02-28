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
                dir('$VERSION') {
                    checkout changelog: false, poll: false, scm: [$class: 'GitSCM',
                             branches: [[name: '*/master']],
                             doGenerateSubmoduleConfigurations: false,
                             extensions: [],
                             submoduleCfg: [],
                             userRemoteConfigs: [[credentialsId: 'm.uluyev@gmail.com', url: 'https://github.com/myuluev/semver.git']]]
                }
            }
        }
    }
}