pipeline {
  agent any
  stages {
    stage('mvn install') {
      steps {
        sh '''pwd
echo $BUILD_NUMBER
mkdir -pv /tmp/$BUILD_NUMBER

cd `pwd`
mv *  /tmp/$BUILD_NUMBER

mkdir -pv /tmp/repo_$BUILD_NUMBER
cp -rp /root/.m2/repository/*  /tmp/repo_$BUILD_NUMBER/

cp -rp /tmp/maven3 /tmp/maven3_$BUILD_NUMBER
sed -i "s/9527/$BUILD_NUMBER/g" /tmp/maven3_$BUILD_NUMBER/conf/settings.xml

cd /tmp/$BUILD_NUMBER
/tmp/maven3_$BUILD_NUMBER/bin/mvn clean install -Dmaven.test.skip=true

 


'''
      }
    }

  }
}