# Minecraft Helm Chart

## Configuration

```yaml
# service account resource configuration
serviceAccount:
  # whether create a service account resource
  create: true

# service resource configuration
service:
  # default service type to use (for this chart LoadBalancer or NodePort is recommended unless using Ingress)
  type: LoadBalancer
  # default port service provides
  port: 25565

# pvc resource configuration
persistentVolumeClaim:
  requests:
    # size of a volume that's provided to minecraft pods (mounted to /data)
    storage: 10Gi

# resource limitations for minecraft pod
resources:
  requests:
    memory: 1Gi
    cpu: 500m
  limits:
    memory: 4Gi
    cpu: 1

# minecraft pods configuration
minecraft:
  # docker image tag to use (image: itzg/minecraft-server)
  tag: latest
  # memory that's given to JVM on startup
  initMemory: 1G
  # maximum amount of memory given to JVM
  maxMemory: 4G
  # your server timezone
  tz: UTC
  # type of a minecraft server (VANILLA, PAPER, etc.)
  type: VANILLA
  # EULA agreement (has to be true for server to work)
  eula: true
  # version of a minecraft to be used
  version: LATEST
  # minecraft world difficulty
  difficulty: easy
  # minecraft server icon url
  icon: https://avatars.githubusercontent.com/u/45029926
  # minecraft world gamemode
  mode: survival
  # message of the day to be displayed
  motd: a kubernetes minecraft server
  # enable pvp
  pvp: true
```
