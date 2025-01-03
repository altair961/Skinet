FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
COPY . /app

WORKDIR /app/ClassLibrary1
RUN ["dotnet", "restore"]

WORKDIR /app/Skinet
RUN ["dotnet", "restore"]

WORKDIR /app/src/AuthenticationService
RUN ["dotnet", "build"]