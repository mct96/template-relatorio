# template-relatorio
template para relatórios de atividades

### Instituto Federal de Mato Grosso

Estudante: Xxxxxxxx Yyyyyyyyyy Zzzzzzzz
Matrícula: 20XX178440206
Curso: Engenharia da Computação
Disciplina: Redes de Computadores II

---
# Configuração da rede ATM

![topology](topology.png)

As atividades consistem em configurar as interfaces dos roteadores R1 e R2 e os switches ATM ATMSWx. Primeiramente, as configurações dos roteadores é como segue:

### R1:
```
configure terminal
int atm1/0
no shutdown
int atm1/0.100 point-to-point
ip address 10.10.10.1 255.255.255.252
pvc 100/101
ip addr 10.10.10.2 broadcast
encapsulation aal5snap
```

#### R2:
```
configure terminal
int atm1/0
no shutdown
int atm1/0.100 point-to-point
ip address 10.10.10.2 255.255.255.252
pvc 100/201
ip addr 10.10.10.1 broadcast
encapsulation aal5snap
```

Já a configuração dos switches ATM é como segue:


### ATMSW1:

![atm1.png](atm1.png)


### ATMSW2:
![atm2.png](atm2.png)


### ATMSW3:
![atm3.png](atm3.png)


|Name|Port|VPI|VCI|Port|VPI|VCI|
|-|-|-|-|-|-|-|
|ATMSW1|1|100|101|3|100|150|
|ATMSW2|2|100|150|3|100|50|
|ATMSW3|3|100|50|1|100|201|
