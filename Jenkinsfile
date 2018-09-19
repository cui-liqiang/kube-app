pipeline {
  agent any
  environment {
    HELM_USERNAME = credentials('HELM_USERNAME')
    HELM_PASSWORD = credentials('HELM_PASSWORD')
}
  stages {
    stage('') {
      steps {
        sh 'echo hello'
      }
    }
    stage('build') {
    steps {
        // 修改为自己的镜像
        sh 'docker build -t registry.cn-hangzhou.aliyuncs.com/k8s-mirrors/kube-app:$BUILD_NUMBER .'
    }
stage('push image') {
    steps {
        withDockerRegistry([credentialsId: 'dockerlogin', url: 'https://registry.cn-hangzhou.aliyuncs.com']) {
            //修改为自己的镜像
            sh 'docker push registry.cn-hangzhou.aliyuncs.com/k8s-mirrors/kube-app:$BUILD_NUMBER'
        }
    }
}
}
  }
}
