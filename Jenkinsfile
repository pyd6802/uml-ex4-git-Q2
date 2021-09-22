podTemplate(containers: [
   containerTemplate(
     name:'maven',
     image: 'maven:3.8.1-jdk-8',
     command: 'sleep',
     args: '30d'
     ),
   ]) {
   node(POD_LABEL) {
       stage('Get a Maven project') {
           git 'https://github.com/pyd6802/uml-ex4-git-Q2.git'
           container('maven') {
               stage('Build a Maven project') {
                   sh '''
                   echo "maven build"
                   mvn -B -DskipTests clean package
                   '''
                   }
            }
       }
    }
 }
