node {
   stage('git pull') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'a4c5b6d7-ecfe-4ef1-aad5-aba0d9401923', url: 'https://github.com/xiaobingchan/maven_springboot_war.git']]])
   }
   stage('mvn Build') {
       sh label: '', script: '/usr/local/maven/bin/mvn clean package'
   }
   stage('deploy') {
       deploy adapters: [tomcat8(credentialsId: 'a4c5b6d7-ecfe-4ef1-aad5-aba0d9401923', path: '', url: 'http://192.168.225.204:8080/')], contextPath: null, war: 'target/*.war'
   }
}
