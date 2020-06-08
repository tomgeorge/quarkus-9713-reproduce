## Build java container 

Get the cert at https://petclinic-petclinic.apps.cluster-teg.sandbox1459.opentlc.com/ and save it in this repo as `custom-cert.crt` 

`mvn package && docker build -f src/main/docker/Dockerfile.jvm -t getting-started-java .`

## Build native container
Get the cert at https://petclinic-petclinic.apps.cluster-teg.sandbox1459.opentlc.com/ and save it in this repo as `custom-cert.crt` 

`mvn clean package -Pnative && docker build -f src/main/docker/Dockerfile.native -t getting-started-native .`

# Reproducing

`docker run --net=host -e REQUEST_URI=https://petclinic-petclinic.apps.cluster-teg.sandbox1459.opentlc.com getting-started-java` 

Will work

`docker run --net=host -e REQUEST_URI=https://petclinic-petclinic.apps.cluster-teg.sandbox1459.opentlc.com getting-started-java` 

Will fail with a `PKIX path building failed` message.
