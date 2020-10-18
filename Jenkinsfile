node {
   stage ('SCM Checkout'){
      git 'https://github.com/Madheswaransekar/UMSL'
   }
    stage ('Compile package'){
        // Get maven home path
        def mvnHome = tool name: 'maven', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }
}
