# gofrrsockets
gofrrsockets is a client library that can be used to send commands to FRR's daemon UNIX sockets. The library provides a safer (forking cmd's can be dangerous) and faster (approx. 8x faster) way of interacting with FRR.

## Supported FRR Daemons
The following FRR Daemons are supported:
 - zebra
 - bgpd
 - ospfd
 - ospf6d
 - ripd
 - ripngd
 - isisd
 - pimd
 - ldpd
 - nhrpd
 - eigrpd
 - babeld

## Example

```
dirPath := /var/run/frr
timeout := time.Duration(time.Second*20)
conn = sock.NewConnection(dirPath, timeout)

output, err := conn.ExecBGPCmd("show bgp summary")
if err != nil {
    return err
}

fmt.Println(string(output))
```
