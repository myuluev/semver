pipeline {
    agent any
//    environment {
//        VERSION = VersionNumber([
//        versionNumberString : '1.0.${BUILD_DAY}',
 //       projectStartDate : '2020-01-01',
  //      PrefixVariable : 'v.'
   //     ])

        BN = VersionNumber([
        versionNumberString : '${BUILD_MONTH}.${BUILDS_TODAY}.${BUILD_NUMBER}',
        projectStartDate : '2017-02-09',
        versionPrefix : 'v1.'
        ])

    stages {
        stage ('Get Version') {
            steps {
   //             sh 'echo "$VERSION"';
                sh 'echo "$BN"';
            }
        }
    }
}