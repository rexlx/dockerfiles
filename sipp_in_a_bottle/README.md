this will build a centos container that runs sipp. add your sipp args to the docker run command.

docker run --name foo -d -p 5060/udp YOUR-DOCKER-IMAGE-NAME-HERE -sn uac SOME-SERVER-HERE -r 9999 
