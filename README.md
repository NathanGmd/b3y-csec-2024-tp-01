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

[Fichier de configuration sshs_config](https://github.com/NathanGmd/b3y-csec-2024-tp-01/blob/main/sshd_config)

# Part IV : Gestion d'utilisateurs

### Création de mot de passe conforme
```
while :; do
    pass=$(tr -dc 'A-Za-z0-9!@#$%^&*()_+' < /dev/urandom | head -c 14)
    if [[ "$pass" =~ [A-Z] ]] && [[ "$pass" =~ [a-z] ]] && [[ "$pass" =~ [0-9] ]] && [[ "$pass" =~ [[:punct:]] ]]; then
        echo "Mot de passe généré : $pass"
        break
    fi
done
```

[Droits Posix](https://github.com/NathanGmd/b3y-csec-2024-tp-01/blob/main/droits-posix)

[Access Control Lists](https://github.com/NathanGmd/b3y-csec-2024-tp-01/blob/main/ACLs)

[Attributes](https://github.com/NathanGmd/b3y-csec-2024-tp-01/blob/main/attributes)

[Attributes](https://github.com/NathanGmd/b3y-csec-2024-tp-01/blob/main/sudoers)

Alysha a accès à un shell root via cat /idea avec les privilège de suha en admins
Liam aussi vu qu'il a les privilèges root de daniel
Même chose pour lev
Jakub aussi vu qu'il a les privilèges de liam qui a les privilèges de daniel

# V. FTP

[vsftpd.conf](https://github.com/NathanGmd/b3y-csec-2024-tp-01/blob/main/vsftpd)

```
sudo yum install vsftpd
sudo mkdir /etc/ssl/private
sudo openssl req -x509 -newkey rsa:4096 -keyout /etc/ssl/private/vsftpd.key -out /etc/ssl/private/vsftpd.crt -days 365 -nodes
sudo systemctl restart vsftpd
sudo firewall-cmd --permanent --add-service=ftp
sudo firewall-cmd --permanent --add-port=30000-31000/tcp  # Ports passifs
sudo firewall-cmd --reload
```
