[Официальная вики](https://suricata.readthedocs.io/en/suricata-6.0.2/rules/file-keywords.html)


```
alert tcp $EXTERNAL_NET any -> $HOME_NET 443 (msg:"!!!!!!!!!Non-TLS on TLS port"; ﬂow:to_server; app-layer-protocol:!tls; )


sha256sum demon_slayer.jpeg                              127 ↵ maxim@ubuntu
2d684774a94620a0377082a9a4d8fc7ff37c88552e07c5d41f1721c014d31084



alert tcp any any -> any any (msg:"FIN_SCAN";
ﬂow:stateless; ﬂags:F; classtype:attempted-recon;)


alert tcp 10.10.58.245 any -> 10.10.58.248 any (msg: "Xmas-SCAN"; flow:stateless; flags:UPF; classtype:attempted-recon)

alert tcp 10.10.58.245 any -> 10.10.58.248 443 (msg:"Non-TLS onTLS port"; ﬂow:to_server; app-layer-protocol:!tls;sid:2230034;)
alert ip any any -> any 53 (msg: "DNS-request"; app-layer-protocol:dns; sid:2230035;)


alert ip any any -> any any ( msg: "Rule all for PDF's"; fileext:"pdf"; sid:2230040;)
alert ip any any -> any any ( msg: "Rule for one file - demon_slayer.jpeg"; filename:"demon_slayer.jpeg"; sid:2230041;)
alert ip any any -> any any ( msg: "Rule 2 for one file - demon_slayer.jpeg"; filesha256:2d684774a94620a0377082a9a4d8fc7ff37c88552e07c5d41f1721c014d31084; sid:2230042;)


sudo suricata -c /etc/suricata/suricata.yaml -i enp3s0


alert ftp any any -> any any ( msg: "Rule all for PDF's(FTP)"; fileext:"pdf"; filestore; sid:2230046;)
alert http any any -> any any ( msg: "Rule all for PDF's(HTTP)"; fileext:"pdf"; filestore; sid:2230047;)
sudo nano /etc/suricata/suricata.yaml
```

