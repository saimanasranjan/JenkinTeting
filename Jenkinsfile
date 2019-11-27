node{
 stage('Checkout'){
  git 'https://github.com/saimanasranjan/JenkinTeting'
 }
 stage('build'){
  def gradleRp ="Gradle-4.3" 
  def buildInfo = gradleRp.run.rootDir:"JenkinTeting/demo/",buiilsFile:'build.gradle',tasks:'clean artifactoryPublish'
  echo('Hi')
 }
}
