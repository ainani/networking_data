### Iperf Network Throughput Testing.
- Potentially used to measuring the network bandwidth throughput between two systems available over IP networks.
- Used in measuring bandwidth, delay, jitter, data loss including TCP/UDP Performance and network throughput on available bandwidth on network.
- Iperf operates in a client and server mode. It’s open source and cross-platform supports variety of operating system

## Useful Commands

| S.No. | Command                      | Help                                            |
|-------|------------------------------|-------------------------------------------------|
| 1     | iperf -s                     | turn one of the systems in to the Iperf server  |
| 2     | iperf -c <SERVER_IP_ADDRESS> | turn one of the systems in to the Iperf client  |

Default arguments, 
- Protocol: TCP --> To change the interface pass ```-u``` for UDP  
- Port: 5001 --> use -p <port> to use different port
- Bind Interface --> use -b <ip_address> or <bind_interface> to permit specific IP or bind interface

**Example**
Client Side:
 - ❗Refer (./images/client.png)

Server Side:
 - ❗Refer (./images/server.png)