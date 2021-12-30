https://docs.microsoft.com/en-us/learn/modules/build-web-api-aspnet-core/

# Classic run
dotnet run
https://localhost:7078/weatherforecast
dotnet build

# Containerized run :
dotnet publish -c Release
docker build -t contosopizza -f Dockerfile .
docker run -p 8080:80 --name contosopizza contosopizza
http://localhost:8080/weatherforecast


# Keycloak :
docker run -d -p 9090:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:16.1.0
http://localhost:9090/auth/

# Simulate load :
On Cygwin/GitBash or any *nix terminal :
#i=0
#while [ $i -le 10 ];
#do
# curl  https://localhost:7078/Pizza -k -X POST -H 'Content-Type:application/json' -d '{"name":"pizza${i}", "isGlutenFree":false}'
#i=$((i+1))
#done