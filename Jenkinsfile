pipeline {
  agent any
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
}
  }
}
