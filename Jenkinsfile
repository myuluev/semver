pipeline {
    environment {
        tag = VersionNumber([
             versionNumberString :'${BUILD_MONTH}.${BUILDS_TODAY}.${BUILD_NUMBER}',
             projectStartDate : '2017-02-09',
             versionPrefix : 'v1.'
             ])
    }

    stages {
        stage('Variables Print')
            steps{
                echo tag
            }
    }
}