FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build-env
WORKDIR /app


COPY *.csproj .

RUN dotnet restore

COPY . ./

RUN dotnet publish --no-retore -c Release -o out

FROM mcr.microsoft.com7dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build-env /app/out .
ENTRYPOINT ["dotnet","Api.dll"]