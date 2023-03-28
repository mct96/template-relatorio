# template-relatorio
template para relatórios de atividades

### Instituto Federal de Mato Grosso

Estudante: Xxxxxxxx Yyyyyyyyyy Zzzzzzzz
Matrícula: 20XX178440206
Curso: Engenharia da Computação
Disciplina: Redes de Computadores II

---
# Configuração da rede ATM

![90f747cba412372cd4af52a4e20d7fd3.png](:/adbde624264c48599743b7458ed1a2df)

As atividades consistem em configurar as interfaces dos roteadores R1 e R2 e os switches ATM ATMSWx. Primeiramente, as configurações dos roteadores é como segue:

R1:
```
configure terminal
int atm1/0
no shutdown
int atm1/0.100 point-to-point
ip address 10.10.10.1 255.255.255.252
pvc 100/101
ip address 10.10.10.2 broadcast
encapsulation aal5snap
```

R2:
```
configure terminal
int atm1/0
no shutdown
int atm1/0.100 point-to-point
ip address 10.10.10.2 255.255.255.252
pvc 100/201
ip address 10.10.10.1 broadcast
encapsulation aal5snap
```

Já a configuração dos switches ATM é como segue:

ATMSW1:
![855893a4789dd97ad39dcb7c832a24de.png](:/db6961bb1f0c403095ea65743d93ee24)

ATMSW2:
![a514defbc875718381bb834b6e53a8d5.png](:/f57f648494c64b3991ec407c219dbdd3)

ATMSW3:
![8f0dae744dc986141ebf9928e489fbb6.png](:/ee1c61d4e483443ca5ef4a5c942de9c6)


|Name|Port|VPI|VCI|Port|VPI|VCI|
|-|-|-|-|-|-|-|
|ATMSW1|1|100|101|3|100|150|
|ATMSW2|2|100|150|3|100|50|
|ATMSW3|3|100|50|1|100|201|
