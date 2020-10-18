node {
   stage ('SCM Checkout'){
      git 'https://github.com/Madheswaransekar/UMSL'
   }
    stage ('Compile package'){
        sh 'mvn package'
    }
}
