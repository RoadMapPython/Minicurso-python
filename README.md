# Minicurso-python
####Pedra papel e tesoura com interface grafica utilizando python<br/>

===================|📚Introdução📚|=====================<br/>
O projeto Roadmap Python é destinado as pessoas que aprenderam python tanto na graduação quanto no tecnico consigam aprender para treinar suas habilidades. Na live reproduziremos o jogo pedra papel e tesoura de forma rápida e fácil de aprender, utilizando a nossa querida linguagem de programação python.
Neste Readme você irá encontrar todos os conceitos abordados na live ,de uma forma textual e didatica.

Nesse primeiro momento realizaremos a criação de um jogo de Pedra, Papel e Tesoura de uma forma mais simples sem interface grafica.
Obs: o código completo e o dicionario ficam no final do Readme<br/>

====================|⚙️Construindo o código⚙️|=====================<br/>
Primeiro iremos perguntar ao usuário o que ele vai escolher<br/>

print("-"*15)<br/>
print("1 - Pedra\n2 - Papel\n3 - Tesoura")<br/>
print("-"*15)<br/>
Jogador = int(input("Escolha uma das opções"))<br/>
<br/>

Ok agora nosso jogador pode escolher umas das 3 opções

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
from random import randint
from PIL import ImageTk,Image
from tkinter import *



tela=Tk()

maquina = randint(1,3)
# 1- Pedra , 2 - Papel e 3 - Tesoura 

print(maquina)


# Função Pedra
def Pedra():

  jogadajogador["text"]="Voce jogou Pedra"

  if maquina==1:
    Empate["text"]="Empate"
    jogadamaquina["text"]="A maquina jogou Pedra"

  elif maquina==2:
    Derrota["text"]="Derrota"
    jogadamaquina["text"]="A maquina jogou Papel"

  elif maquina==3:
     Vitoria["text"]="Vitoria"
     jogadamaquina["text"]="A maquina jogou Tesoura"



def Papel():

  jogadajogador["text"]="Voce jogou Papel"


  if maquina ==2:
    Empate["text"]="Empate"
    jogadamaquina["text"]="A maquina jogou Papel"

  elif maquina==1:
    Vitoria["text"]="Vitoria"
    jogadamaquina["text"]="A maquina jogou Pedra"  

  elif maquina==3:
    Derrota["text"]="Derrota"
    jogadamaquina["text"]="A maquina jogou Tesoura"


def Tesoura():

  jogadajogador["text"]="Voce jogou Tesoura"


  if maquina ==3:

    Empate["text"]="Empate"
    jogadamaquina["text"]="A maquina jogou Tesoura"


  elif maquina==1:
     Derrota["text"]="Derrota"
     jogadamaquina["text"]="A maquina jogou Pedra"

  elif maquina==2:
    Vitoria["text"]="Vitoria"
    jogadamaquina["text"]="A maquina jogou Papel"     


photo1 = PhotoImage(file="pedra.png")
photoimage=photo1.subsample(3,3)

botao=Button(tela,image=photo1,command=Pedra)
botao.place(x=100,y=100)

photo =PhotoImage(file="papel.png")
photoimage=photo.subsample(10,5)

botao1=Button(tela,image=photo,command=Papel)
botao1.place(x=300,y=100)


photo2= PhotoImage(file="tesoura.png")
photoimage=photo2.subsample(1,1)

botao2=Button(tela,image=photo2,command=Tesoura)
botao2.place(x=500,y=100)


Titulo=Label(tela, text="Pedra , Papel e Tesoura",anchor=W).place(x=280,y=10, width=150,height=20)

Vitoria=Label(tela, text="",foreground="Green")
Vitoria.place(x=300,y=250)

Derrota=Label(tela, text="", foreground="Red")
Derrota.place(x=300,y=250)

Empate=Label(tela, text="",foreground="Gray")
Empate.place(x=300,y=250)


jogadajogador=Label(tela, text="")
jogadajogador.place(x=300,y=300)


jogadamaquina=Label(tela, text="")
jogadamaquina.place(x=300,y=350)


Sair=Button(tela,text="Sair",command=exit)
Sair.place(x=300,y=400)


tela.geometry("800x400+0+0")
tela.configure(background="#800080")
tela.mainloop()
