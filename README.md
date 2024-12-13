# Manipulando-a-rede

  
### Ferramentas  :hammer_and_wrench:

- Kali Linux :desktop_computer:
- ETTERCAP :space_invader:
- Metasploitable 

# Introdução
Ettercap é um conjunto abrangente para ataques Man in the Middle, possui sniffing de conexões ao vivo, filtragem de conteúdo em tempo real e muitos outros recursos.

# Modos de operação
-Baseado em ip: os pacotes são filtrados com base na origem e destino ip.
-Mac: os pacotes são filtrados com base no endereço MAC útil para sniffing conexões através de um gateway.
-ARP: utiliza o envenenamento ARP para sniffar em uma LAN entre dois hosts (full - duplex)
-PublicARP: usa o envenamento ARP para sniffar em uma LAN de um host vitima para todos os outros (half - duplex)

# Prática
Iniciando o kali como root e com o comando ```ettercap -G``` o nosso ettercap, como podemos ver a figura abaixo.

![image](https://github.com/user-attachments/assets/6292d8ad-e41e-43fa-bd83-6fc540de8772)

---

Primeiro passo vamos fazer um scanner dos hosts.Logo após definir meus Targets com ip que eu escolhi.

![image](https://github.com/user-attachments/assets/ab4f8741-7384-4605-9307-26f4560fcdb7)

---

Proximo passo iniciar meu sniffer, mas antes precisamos executar um comando no nosso terminal para fazer um redirecionamento do trafego 

ip_forward inicializa como 0 , mas se habilitarmos com 1, poderemos fazer o redirecionamento

Comando : ```echo 1 > /proc/sys/net/ipv4/ip_forward```

![image](https://github.com/user-attachments/assets/d5773760-2bb2-4f04-b302-ebe5bed31236)

---
Precisamos fazer o envenenamento do ARP dessa forma confundir a tabela de roteamento dos host e conseguir capturar o trafego.

Tudo que estiver entre meu Windows 7 e meu Metasploitable vou capturar no kali linux sendo o Man in the Middle.

![image](https://github.com/user-attachments/assets/25fa0311-edcd-4a62-8568-750b5ebf1263)

![image](https://github.com/user-attachments/assets/d1a70f64-7c46-4a2f-9bd9-5ab00de6087d)


---
Utilizando o Wireshark podemos verificar que no filtro ARP  temos uma conversa entre a maquina windows 7 e nosso Metasploitable.

![image](https://github.com/user-attachments/assets/123ad0ae-fd8a-418a-b1d1-2da82af982d7)


![image](https://github.com/user-attachments/assets/f5bf2b1c-990d-4fb5-b4ac-6df71ea4057d)



