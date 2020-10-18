node {
   stage ('SCM Checkout'){
      git 'https://github.com/Madheswaransekar/UMSL'
   }
    stage ('Compile package'){
        // Get maven home path
        def mvnHome = tool name: 'maven', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }
    
    stage ('sonarqube analysis'){
        def mvnHome = tool name: 'maven', type: 'maven'
        withSonarQubeEnv('sonar'){
        sh "${mvnHome}/bin/mvn sonar:sonar"
        }
    }
    
    stage ('submit stack'){
        steps{
        sh "aws cloudformation create-stack --stack-name <<stack_name>> --template-body file:// 
        }
    }
}
