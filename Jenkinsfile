//def ReleaseDir = "c:\inetpub\wwwroot"
pipeline {
			agent any
			environment {
       			dotnet ='C:\\Program Files (x86)\\dotnet\\'
       				}
			triggers {
        		pollSCM 'H * * * *'
    				}		
			stages {
				stage('Check out'){
					steps{
						checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '825fc4d4-4161-4170-9587-28a936f82af6', url: 'https://github.com/miraclekuro/asp.net-core']]])
					}
				}
				// stage('Restore packages'){
  			 	// 	steps{
     			//  bat "dotnet restore \\Sample.csproj"
    			// 	}
  				// }
				stage('Build') {
    					steps {
							bat 'dotnet build E:\Sample\Sample.csproj'
    					    // bat "\"${tool 'MSBuild'}\" \\Sample.csproj /p:DeployOnBuild=true /p:DeployDefaultTarget=WebPublish /p:WebPublishMethod=FileSystem /p:SkipInvalidConfigurations=true /t:build /p:Configuration=Release /p:Platform=\"Any CPU\" /p:DeleteExistingFiles=True /p:publishUrl=c:\\inetpub\\wwwroot"
    					}
				}
			}
}