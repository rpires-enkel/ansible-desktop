# Servidor

## Instalação ##
```
sudo passwd
su
cd
apt install git ansible -y
git clone https://github.com/rpires-enkel/ansible-servidor
ansible-playbook ~/ansible-servidor/playbook_CALEX.yaml
```

## Comandos ##
Para listar usuários do samba
```
pdbedit -L -v
```
para criar novos usuarios
```
./samba_adduser <usuario>
```
para apagar usuarios
```
./samba_deluser <usuario>
```
Para deletar informacoes de usuario gravadas no Windows
```
net use * /del
```
chgrp -R comercial /usr/local/comercial
chmod 2775 /usr/local/comercial
