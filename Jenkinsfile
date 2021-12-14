bat '''node {
  stage(\'SCM\') {
    git \'https://github.com/foo/bar.git\'
  }
  stage(\'Build + SonarQube analysis\') {
    def sqScannerMsBuildHome = tool \'Scanner for MSBuild 4.6\'
    withSonarQubeEnv(\'My SonarQube Server\') {
      bat "${sqScannerMsBuildHome}\\\\SonarQube.Scanner.MSBuild.exe begin /k:sonarqube
      bat \'MSBuild.exe /t:Rebuild\'
      bat "${sqScannerMsBuildHome}\\\\SonarQube.Scanner.MSBuild.exe end"
    }
  }
}'''