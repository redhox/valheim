#  valheim
 
 
     git clone https://github.com/thorkseng/pi4valheim.git
  .




    sudo podman build -t valheim-base:v1 -f valheim.Dockerfile
.


    sudo podman run --name valheim --network host -v /home/coulm/valheim_data:/root/valheim_data:rw -it valheim-base:v1 


docker_compose x86

  
    version: "2"
    
    services:
      valheim-server:
        image: lloesche/valheim-server
        restart: unless-stopped
        cap_add:
          - sys_nice
        stop_grace_period: 120s
        ports:
          - "2456-2457:2456-2457/udp"
        volumes:
          - ./config:/config
          - ./data:/opt/valheim
        environment:
          SERVER_NAME: "My Server"
          WORLD_NAME: "save_name"
          SERVER_PASS: "password"

format

  
    ├── config
    │   └── worlds_local
    └── data
        ├── dl
        │   └── server
        │       ├── docker
        │       ├── linux64
        │       ├── steamapps
        │       │   ├── downloading
        │       │   │   └── 896660
        │       │   └── temp
        │       │       └── 896660
        │       └── valheim_server_Data
        │           ├── Managed
        │           ├── MonoBleedingEdge
        │           │   ├── etc
        │           │   │   └── mono
        │           │   │       ├── 2.0
        │           │   │       │   └── Browsers
        │           │   │       ├── 4.0
        │           │   │       │   └── Browsers
        │           │   │       ├── 4.5
        │           │   │       │   └── Browsers
        │           │   │       └── mconfig
        │           │   └── x86_64
        │           ├── Plugins
        │           ├── Resources
        │           └── StreamingAssets
        └── server
            ├── docker
            ├── linux64
            └── valheim_server_Data
                ├── Managed
                ├── MonoBleedingEdge
                │   ├── etc
                │   │   └── mono
                │   │       ├── 2.0
                │   │       │   └── Browsers
                │   │       ├── 4.0
                │   │       │   └── Browsers
                │   │       ├── 4.5
                │   │       │   └── Browsers
                │   │       └── mconfig
                │   └── x86_64
                ├── Plugins
                ├── Resources
                └── StreamingAssets
