# b3y-csec-2024-tp-01

# Part I : Filtrey des paqueys

```
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3 enp0s8
  sources: 10.1.1.0/24
  services:
  ports: 1025/tcp
  protocols:
  forward: yes
  masquerade: no
  forward-ports:
  source-ports:
  icmp-blocks:
  rich rules:
```

# Part II : PAM

[Fichier de configuration pwquality.conf](https://github.com/NathanGmd/b3y-csec-2024-tp-01/blob/main/pwquality.conf)

# Part III : OpenSSH
