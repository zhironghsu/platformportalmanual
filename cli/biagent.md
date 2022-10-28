# Advantech Edge365 DPM Agent Service (CLI)

```sh
Usage:
  edge365-agent [flags]
  edge365-agent [command]

Available Commands:
  conn        Apply connection setting
  help        Help about any command
  service     Manage service

Flags:
  -a, --address string                The IP address on which to listen for the --port port.
                                      If blank, all interfaces will be used (0.0.0.0 for all IPv4
                                      interfaces and :: for all IPv6 interfaces). (default "")
  -p, --port int                      The port on which to serve HTTPS with
                                      authentication and authorization.
                                      (default 8744)
      --tls-cert-file string          File containing the default x509 Certificate for HTTPS.
                                      (CA cert, if any, concatenated after server cert).
                                      If --tls-cert-file and --tls-private-key-file are not provided,
                                      a self-signed certificate and key are generated for the public address
                                      and saved to the --tls-key-dir.
                                       (default "cert.crt")
      --tls-private-key-file string   File containing the default x509 private key
                                      matching --tls-cert-file.
                                       (default "key.pem")
      --tls-key-dir string            Location of --tls-cert-file and --tls-private-key-file
                                       (default "/etc/xdg/Advantech/.edge365-agent/keys")
      --insecure-address string       The IP address on which to serve the --insecure-port
                                      (set to 0.0.0.0 for all IPv4 interfaces and :: for all IPv6 interfaces).
      --insecure-port int             The port on which to serve unsecured,
                                      unauthenticated access. Set to 0 to disable. (default 8789)
      --jwt-auth-server-url string    Authentication Server URL
                                       (default "https://localhost:6443")
      --jwt-cert-file string          File containing the default x509 Certificate for JWT.
                                      (CA cert, if any, concatenated after server cert).
                                       (default "cert.crt")
      --jwt-cert-dir string           Location of --jwt-cert-file
                                       (default "/etc/xdg/Advantech/.edge365-agent/keys/jwt")
      --jwt-check-interval duration   Duration that check and download JWT certificate
                                      from the authentication server. (default 5s)
      --config string                 Location of config files
                                       (default "/etc/xdg/Advantech/.edge365-agent")
  -d, --debug                         enable debug output
  -h, --help                          help for edge365-agent
      --version                       version for edge365-agent

Use "edge365-agent [command] --help" for more information about a command.
```

* `service` command

  ```sh
  Manage service

  Usage:
    edge365-agent service [flags]
    edge365-agent service [command]

  Available Commands:
    install     install service
    restart     restart service
    start       start service
    stop        stop service
    uninstall   uninstal service

  Flags:
    -h, --help   help for service

  Global Flags:
        --config string   Location of config files
                           (default "/etc/xdg/Advantech/.edge365-agent")
    -d, --debug           enable debug output

  Use "edge365-agent service [command] --help" for more information about a command.
  ```

* `conn` command

  ```sh
  Apply connection setting

  Usage:
    edge365-agent conn [flags]
    edge365-agent conn [command]

  Available Commands:
    disable     Set connection to Disabled state
    enable      Set connection to Enabled state
    mac         Get MAC address for the connection
    reset       Reset connection settings
    status      Get connection status

  Flags:
    -a, --address string    The MQTT broker host address (i.e. localhost, 127.0.0.1)
    -p, --port int          The MQTT broker port number
    -u, --username string   Username for the MQTT connection
    -P, --password string   Password for the MQTT connection
        --enable-tls        Enable TLS connection
        --over-ws           Enable MQTT over WebSocket
        --cs string         The Azure IoTHub Device Connection String
    -h, --help              help for conn

  Global Flags:
        --config PathString   Location of config files

    -d, --debug               enable debug output (default true)

  Use "edge365-agent conn [command] --help" for more information about a command.

  ```
