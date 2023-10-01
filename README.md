# Metrics

## Containers
| Name          | URL                                     |
|---------------|-----------------------------------------|
| cadvisor      | [https://cadvisor.gavanlamb.com](https://grafana.gavanlamb.com/)   |
| node_exporter | N/A                                     |
| prometheus    | [https://prometheus.gavanlamb.com](https://prometheus.gavanlamb.com/) |

Update the metrics-addr
* Linux 
    `/etc/docker/daemon.json`
    ```json
{
    "metrics-addr" : "192.168.50.**:9323",
    "experimental" : true
}
    ```
  
* Windows Server
    `C:\ProgramData\docker\config\daemon.json`
    ```powershell
    $contentToAdd = @"
    {
        "experimental": true,
        "metrics-addr" : "192.168.50.**:9323",
        "hosts": [
            "npipe:////./pipe/docker_engine_windows"
        ]
    }
    "@

    Set-Content -Path ./daemon.json -Value $contentToAdd
    ```
