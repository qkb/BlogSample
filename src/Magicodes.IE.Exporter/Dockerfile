<<<<<<< HEAD
FROM ccr.ccs.tencentyun.com/magicodes/aspnetcore-runtime:latest AS base

#WORKDIR /src
COPY simsun.ttc /usr/share/fonts/simsun.ttc
=======
#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.
>>>>>>> 062cf069d69f6c33e3ee6502436e2b5ec862366f

FROM ccr.ccs.tencentyun.com/magicodes/aspnetcore-runtime:latest AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443
COPY /src/Magicodes.IE.Exporter/simsun.ttc /usr/share/fonts/simsun.ttc

<<<<<<< HEAD
FROM mcr.microsoft.com/dotnet/core/sdk:latest AS build
#WORKDIR /src
COPY ["Magicodes.IE.Exporter.csproj", "Magicodes.IE.Exporter/"]
RUN dotnet restore "Magicodes.IE.Exporter/Magicodes.IE.Exporter.csproj"
COPY . .
#WORKDIR "Magicodes.IE.Exporter"
=======
FROM mcr.microsoft.com/dotnet/core/sdk:3.1-buster AS build
WORKDIR /src
COPY ["src/Magicodes.IE.Exporter/Magicodes.IE.Exporter.csproj", "src/Magicodes.IE.Exporter/"]
RUN dotnet restore "src/Magicodes.IE.Exporter/Magicodes.IE.Exporter.csproj"
COPY . .
WORKDIR "/src/src/Magicodes.IE.Exporter"
>>>>>>> 062cf069d69f6c33e3ee6502436e2b5ec862366f
RUN dotnet build "Magicodes.IE.Exporter.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "Magicodes.IE.Exporter.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
<<<<<<< HEAD
COPY --from= publish /app/publish .
=======
COPY --from=build /app/publish .
>>>>>>> 062cf069d69f6c33e3ee6502436e2b5ec862366f
ENTRYPOINT ["dotnet", "Magicodes.IE.Exporter.dll"]