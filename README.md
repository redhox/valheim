#  valheim
 
 
     git clone https://github.com/thorkseng/pi4valheim.git
  .


    sudo podman build -t valheim-base:v1 -f valheim.Dockerfile
.

    sudo podman run --name valheim --network host -v /home/coulm/valheim_data:/root/valheim_data:rw -it valheim-base:v1 
