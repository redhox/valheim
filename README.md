#  valheim
 
 
     git clone https://github.com/thorkseng/pi4valheim.git
  .




    sudo podman build -t valheim-base:v1 -f valheim.Dockerfile
.


    sudo podman run --name valheim --network host -v /home/coulm/valheim_data:/root/valheim_data:rw -it valheim-base:v1 


docker_compose x86

  
      version: '3.3'
      services:
       valheim-server:
         container_name: valheim-server
         image: lloesche/valheim-server
         cap_add:
           - sys_nice
         stop_grace_period: 120s
         ports:
           - 2456-2457:2456-2457/udp
         volumes:
           - $HOME/valheim-server/config:/config
           - $HOME/valheim-server/data:/opt/valheim
         environment:
           - SERVER_NAME=My Server
           - WORLD_NAME=Neotopia
           - SERVER_PASS=secret
