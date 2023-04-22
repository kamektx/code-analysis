#See https://aka.ms/customizecontainer to learn how to customize your debug container and how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["//wsl$/Ubuntu/home/kamektx3/docker/code-analysis/aspnet/code-analysis/code-analysis.csproj", "//wsl$/Ubuntu/home/kamektx3/docker/code-analysis/aspnet/code-analysis/"]
RUN dotnet restore "//wsl$/Ubuntu/home/kamektx3/docker/code-analysis/aspnet/code-analysis/code-analysis.csproj"
COPY . .
WORKDIR "/src///wsl$/Ubuntu/home/kamektx3/docker/code-analysis/aspnet/code-analysis"
RUN dotnet build "code-analysis.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "code-analysis.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "code-analysis.dll"]