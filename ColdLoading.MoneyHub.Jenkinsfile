node {
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'git@github.com:Camelchen/Selenium.Framework.git'
  
   }
   stage('Build') {
      bat 'nuget restore Selenium.Framework.sln'
      bat "\"${tool 'MSBuild'}\" SolutionName.sln /p:Configuration=Release /p:Platform=\"Any CPU\" "
   }
   stage('Execute') {
      bat 'dotnet Selenium.Droid.ColdLoading/bin/Release/netcoreapp2.1/Selenium.Droid.ColdLoading.dll MoneyHub'
   }
   stage('Archive') {
      archive 'Selenium.Droid.ColdLoading/bin/Release/**' 
   }
}