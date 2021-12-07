# Minicurso-python
####Pedra papel e tesoura com interface grafica utilizando python

O projeto Roadmap Python é destinado as pessoas que aprenderam python tanto na graduação quanto no tecnico consigam aprender para treinar suas habilidades. Na live reproduziremos o jogo pedra papel e tesoura de forma rápida e fácil de aprender, utilizando a nossa querida linguagem de programação python.
Neste Readme você irá encontrar todos os conceitos abordados na live ,de uma forma textual e didatica.

Nesse primeiro momento realizaremos a criação de um jogo de Pedra, Papel e Tesoura de uma forma mais simples sem interface grafica.
Obs: o código completo e o dicionario ficam no final do Readme
====================|⚙️Construindo o código⚙️|=====================<br/>
Primeiro iremos perguntar ao usuário o que ele vai escolher<br/>

print("-"*15)<br/>
print("1 - Pedra\n2 - Papel\n3 - Tesoura")<br/>
print("-"*15)<br/>
Jogador = int(input("Escolha uma das opções"))<br/>
<br/>

Ok ja fizemos nosso inicio de jogo agora o que falta ?

====================|⚙️1° Código completo⚙️|======================<br/>
from random import randint from time import sleep

for i in range(3): possibilidades=("Pedra","Papel","Tesoura") maquina = randint(0,2)
print("-"*15)<br/>
print("1 - Pedra\n2 - Papel\n3 - Tesoura")<br/>
print("-"*15)<br/>
Jogador = int(input("Escolha uma das opções"))<br/>
<br/>
print("JO")
sleep(3)
print("KEN")
sleep(3)
print("PO")
sleep(3)
print("Computador Jogou {}".format(possibilidades[maquina]))
print(" Voce      Jogou {}".format(possibilidades[Jogador]))

if maquina==0:
#pedra
    if Jogador ==0:
      print ("Empate")
    elif Jogador==1:
      print ("Jogador Venceu") 
    elif Jogador==2:
      print("Computador Venceu")


elif maquina==1:
  #Papel
      if Jogador==0:
        print("Computador Venceu") 
      elif Jogador==1:
        print("Empate")
      elif Jogador==2:
        print("Jogador Venceu")

elif maquina==2:
  #Tesoura
      if Jogador==0:
        print("Jogador Venceu")
      elif Jogador==1:
        print("Computador Venceu")
      elif Jogador==2:
        print("Empate")

else:
   print("Movimento Inválido") 
print("\n") print("\n") print("\n")<br/>
====================|⚙️2° Código completo⚙️|======================<br/>
