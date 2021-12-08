# Minicurso-python
##Pedra papel e tesoura com interface grafica utilizando python<br/>

===================|📚Introdução📚|=====================<br/>
O projeto Roadmap Python é destinado as pessoas que aprenderam python tanto na graduação quanto no tecnico consigam aprender para treinar suas habilidades. Na live reproduziremos o jogo pedra papel e tesoura de forma rápida e fácil de aprender, utilizando a nossa querida linguagem de programação python.
Neste Readme você irá encontrar todos os conceitos abordados na live ,de uma forma textual e didatica.

Nesse primeiro momento realizaremos a criação de um jogo de Pedra, Papel e Tesoura de uma forma mais simples sem interface grafica.
Obs: o código completo e o dicionario ficam no final do Readme<br/>

====================|⚙️Construindo o código⚙️|=====================<br/>
* Em um primeiro momento pedimos que o usuário escolha uma das 3 opções , 
```
from random import randint<br/>
print("-"*15)<br/>
print("1 - Pedra\n2 - Papel\n3 - Tesoura")<br/>
print("-"*15)<br/>
jogador = int(input("Escolha uma das opções"))<br/>
```
<br/>

* Utilizamos o randit para a maquina também escolher uma das 3 de forma randomica.<br/>
```maquina = randint(1, 3)```
<br/>

* Agora criaremos 3 funções com nossos if e elif desisivos para o funcionamento do código
```
def Pedra():
def Papel():
def Tesoura():
```

* Cada if chama uma dessas funçôes caso o jogador escolha entre Pedra/Papel/Tesoura<br/>
_Qual o motivo dos ifs decisivos ficarem depois das funções?<br/>
As funções elas devem ser declaradas antes de serem chamadas no código,para assim ter o funcionamento de tal,
se fosse ao contrário apareceria um erro dizendo que nao foi declarada a função._<br/>
```
if jogador == 1:
    Pedra()
elif jogador == 2:
    Papel()
elif jogador == 3:
    Tesoura
```
<br/>

* Agora com a criação de 3 ifs chamando cada uma das funções, iremos colocar nas possibilidades de resposta da máquina
```
def Pedra():
    print('Você jogou pedra')
    if maquina == 1:
        print("empate")
    elif maquina == 2:
        print("derrota")
        print("a maquina jogou papel")
    elif maquina == 3:
        print("Vitoria")
        print("a maquina jogou tesoura")


def Papel():
    print("Você escolheu papel")
    if maquina == 2:
        print("empate")
    elif maquina == 1:
        print("Vitoria")
    elif maquina == 3:
        print("Derrota")


def Tesoura():
    print("Voce jogou Tesoura")
    if maquina == 3:
        print("Empate")
    elif maquina == 1:
        print("Derrota")
    elif maquina == 2:
        print("Vitoria")
 ```

Pronto ,nosso código em python de uma forma simples.
Agora iremos transformar isso tudo em 

====================|⚙️Código Sem interface⚙️|=====================<br/>
from random import randint
print("-"*15)
print("1 - Pedra\n2 - Papel\n3 - Tesoura")
print("-"*15)
jogador = int(input("Escolha uma das opções"))

maquina = randint(1, 3)

print(maquina)


def Pedra():
    print('Você jogou pedra')
    if maquina == 1:
        print("empate")
    elif maquina == 2:
        print("derrota")
        print("a maquina jogou papel")
    elif maquina == 3:
        print("Vitoria")
        print("a maquina jogou tesoura")


def Papel():
    print("Você escolheu papel")
    if maquina == 2:
        print("empate")
    elif maquina == 1:
        print("Vitoria")
    elif maquina == 3:
        print("Derrota")


def Tesoura():
    print("Voce jogou Tesoura")
    if maquina == 3:
        print("Empate")
    elif maquina == 1:
        print("Derrota")
    elif maquina == 2:
        print("Vitoria")


if jogador == 1:
    Pedra()
elif jogador == 2:
    Papel()
elif jogador == 3:
    Tesoura

====================|⚙️Código completo⚙️|======================<br/>
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
tela.mainloop()<br/>
======================================================================<br/>
---Dicionário---<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
