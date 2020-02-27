pipeline {
    agent any
    environment {
        Version_Major = '1'
        Version_Minor  = '0'
        Version_Patch  = '0'
        VERSION = VersionNumber([
        versionNumberString : "${Version_Major}.${Version_Minor}.${BUILD_NUMBER}-${GIT_COMMIT}",
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
    }
}