#FROM nexus.mir:59999/tools/core-dotnet/aspnet:6.0.10-focal AS base
FROM mcr.microsoft.com/dotnet/aspnet:6.0-jammy AS base
WORKDIR /app
#EXPOSE 5000

#FROM nexus.mir:59999/tools/core-dotnet/sdk:6.0.16-jammy-custom AS build
FROM mcr.microsoft.com/dotnet/sdk:6.0-jammy AS build
WORKDIR /src
COPY . /src
RUN dotnet restore WebApplication_DIT_Docker/WebApplication_DIT_Docker.csproj
RUN dotnet build WebApplication_DIT_Docker.sln -c Release -o /app/build
WORKDIR /app/build/
ENV ASPNETCORE_URLS="http://0.0.0.0:5000"
ENTRYPOINT ["dotnet", "WebApplication_DIT_Docker.dll"]
