pipeline {
    agent any
    environment {
            tag = VersionNumber(versionNumberString: '${BUILD_DATE_FORMATTED,"yyyyMMdd"}-develop-${BUILDS_TODAY}');
            }

        stage ('Restore packages'){
        steps {
            script{
            echo "${tag}"
         }
      }
   }
}