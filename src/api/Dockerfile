FROM microsoft/dotnet:2.0-sdk AS build-env
WORKDIR /app
COPY . ./
RUN dotnet publish -c Release -o out -r linux-x64

FROM microsoft/dotnet:2.0-runtime 
WORKDIR /app
COPY --from=build-env /app/out ./
ENTRYPOINT ["dotnet", "api.dll"]