# desktop

Para listar usuários do samba
pdbedit -L -v

para criar novos usuarios
./samba_adduser <usuario>

para apagar usuarios
./samba_deluser <usuario>

chgrp -R comercial /usr/local/comercial

chmod 2775 /usr/local/comercial

Para deletar informacoes de usuario gravadas no Windows
net use * /del
