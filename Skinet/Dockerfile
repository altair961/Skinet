# This stage is used to build the service project
FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
ARG BUILD_CONFIGURATION=Release
COPY . /app
WORKDIR /app/ClassLibrary1
RUN ["dotnet", "restore"]

WORKDIR /app/Skinet
RUN ["dotnet", "restore"]

WORKDIR /app/Skinet
RUN ["dotnet", "build"]

# This stage is used to publish the service project to be copied to the final stage
FROM build AS publish
ARG BUILD_CONFIGURATION=Release
RUN dotnet publish "./Skinet.csproj" -c $BUILD_CONFIGURATION -o /app/publish /p:UseAppHost=false

