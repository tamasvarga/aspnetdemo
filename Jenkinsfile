node {
	stage 'Checkout'
		checkout scm

	stage 'Build'
		def msbuild = tool name: 'msbuld', type: 'hudson.plugins.msbuild.MsBuildInstallation'
		bat 'c:\\nuget.exe restore AspNetHelloWorld.sln'
		bat "\"${tool 'MSBuild'}\" AspNetHelloWorld.sln /p:Configuration=Release /p:Platform=\"Any CPU\""

	stage 'Archive'
		archive 'ProjectName/bin/Release/**'

}
