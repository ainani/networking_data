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
 - ❗Refer [Client Side Iperf](./images/client.png)

Server Side:
 - ❗Refer [Server Side Iperf](./images/server.png)



### Server
- In server mode using -s flag, it will listen on port 5201 by default
- Specify the format (k, m, g for Kbits, Mbits, Gbits or K, M, G for KBytes, Mbytes, Gbytes)
- Report using the -f switch
  ```iperf3 -s -f K``` 

- If port 5201 is being used by another program on your server, you can specify a different port (e.g 3000) using the -p switch
 ```iperf3 -s -p 3000```
- Run server mode as daemon and Writing server log to a file 
  ```iperf3 -s -D > iperf3log```

### Client
- Runs on user's local machine (the client) where the actual benchmarking takes place
- Specify the host on which the server is running on (either using its IP address or domain or hostname)
  ```iperf3 -c 192.168.10.1 -f K```
- Set the window size/socket buffer size using the -w flag
  ```iperf3 -c 192.168.10.1 -f K -w 500K```	
- Reverse mode where the server sends and the client receives, add the -R switch
 ```iperf3 -c 192.168.10.1 -f K -w 500K -R```
- Bidirectional test, measure bandwidth in both directions simultaneously, use the -d option.
  ```iperf3 -c 192.168.10.1 -f K -w 500K -d```
- Server results in the client output, use the --get-server-output option
  ```iperf3 -c 192.168.10.1 -f K -w 500K -R --get-server-output```
- Set the number of parallel client streams (5 in this example), which run at the same time, using the -P options
  ```iperf3 -c 192.168.10.1 -f K -w 500K -P 5```