pipeline {
    agent any
    environment {
            VERSION = VersionNumber([
                versionNumberString : '1.0.${BUILD_DAY}',
                projectStartDate : '2020-01-01',
                PrefixVariable : ''
                ])
            }

        stage ('Restore packages'){
        steps {
            sh 'echo "$VERSION"';
         }
   }
}