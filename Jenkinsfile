pipeline {
    agent any
    environment {
      Version_Major = '1'
      Version_Minor  = '0'
      Version_Patch  = '0'
      VERSION = VersionNumber([
          versionNumberString: '${Version_Major}.${Version_Minor}.${Version_Patch}.${BUILD_NUMBER}',
       worstResultForIncrement: 'SUCCESS'

      ]);
    }
        stage ('Restore packages'){
        steps {
            script{
            echo "${VERSION}"
         }
      }
   }
}