pipeline {
    agent any
    environment {
//        VERSION = VersionNumber([
//        versionNumberString : '1.0.${BUILD_DAY}',
 //       projectStartDate : '2020-01-01',
  //      PrefixVariable : 'v.'
   //     ])

        VERSION = VersionNumber([
        versionNumberString : '${BUILD_MONTH}.${BUILDS_TODAY}.${BUILD_NUMBER}',
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