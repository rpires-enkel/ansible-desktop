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

## Windows 2012 Server ##
```
ServerManager
	Add roles and features -> Next -> Role-Based (Next) -> Selecionar a própria máquina (Next)
		Active Directory Domain Services (Next) -> Next -> Next -> Install
		*IMPORTANTE - não promover o servidor para domain controller. Simplesmente clicar em "Close"
			Adicionar a máquina no DOMAIN
				dsa
```

## Testes ##
Todos os testes devem funcionar:
```
host -t SRV _kerberos._udp.calex.local.br
host -t SRV _ldap._tcp.calex.local.br
host -t A calex.local.br

# Aqui precisa do DNS Forwarder em smb.conf apontando pra 8.8.8.8:
host www.amazon.com
host -t mx amazon.com

kinit administrator@CALEX.LOCAL.BR
klist

smbclient -L localhost -UAdministrator
smbclient //localhost/netlogon -UAdministrator -c 'ls'
net rpc rights list -U administrator
wbinfo --ping-dc
getent passwd Administrator

```

