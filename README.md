# pfsense-dhcp
Habilitando opção de Class e Member Class

Entre na opção Diagnósticos/Prompt de comando
Execute os comandos abaixo.

cp /etc/inc/services.inc /etc/inc/services.inc.bkp && fetch -q -o /etc/inc/services.inc https://raw.githubusercontent.com/admredesmaiconalves/pfsense-dhcp/master/services.inc


Após concluir execute este outro comando.
cp /usr/local/www/services_dhcp.php /usr/local/www/services_dhcp.php.bkp && fetch -q -o /usr/local/www/services_dhcp.php https://raw.githubusercontent.com/admredesmaiconalves/pfsense-dhcp/master/services_dhcp.php

Feito isso a interface já estará com a opções habilitas.


OBS: Para separar os dispositivos moveis de notebook utilizei o seguinte class para pegar Android, Windows Phone e Iphone.

<img src=dhcp-class.png>

Adicinei dois pools um para notebook que este foi colocado para não ser membro do class "celular".

<code>deny members of "celular"</code>

O outro pool destinado aos dispositivos moveis adicionei como membro.

<code>allow members of "celular"</code>

<img src=member-class.png>
