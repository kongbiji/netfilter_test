# netfilter_test
Example of string filtering in a domain

# Environments setting
```
iptables -F
iptables -A OUTPUT -j NFQUEUE --queue-num 0
iptables -A INPUT -j NFQUEUE --queue-num 0
```
Set up the iptables so that the packets sent and received go through the netfilter queue.

```
$ apt install libmnl-dev
$ apt install libnfnetlink-dev
$ apt install libnetfilter-queue-dev
```


# Build
g++ -o netfilter_test netfilter_test.cpp -lnetfilter_queue

# How to use
```
sudo ./netfilter_test <string to filter>
```
You must execute with root authority; otherwise there will be errors.
