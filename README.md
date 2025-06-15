# .NET Hello World Program


#### Install dotnet tools
`
sudo snap install dotnet --classic
`
#### If you don’t have a project yet, create one
`
dotnet new console -n DotnetJob
cd DotnetJob
`
#### Now you should see:
`
DotnetJob.csproj  Program.cs
`
#### Publish your project
`
dotnet publish -c Release -o ./publish
`
#### Create Dockefile

`FROM mcr.microsoft.com/dotnet/runtime:7.0 AS base`
`WORKDIR /app`
`COPY ./publish .`
`ENTRYPOINT ["dotnet", "DotnetJob.dll"]`

#### Build Dotnet App
`
docker build -t job-dotnet .
`

