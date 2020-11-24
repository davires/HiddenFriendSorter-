# HiddenFriendSorter-
#Sorteador para amigo oculto ou equivalente em PYTHON
from random import *


def inicio():
    print("\n"*50)
    print("Bem-vindo")
    print("Esse projeto trata de um simples sorteador.")
    print("Qualquer erro/dúvida/sugestão favor entrar em contato!")
    print()
    print("                                 ################")
    print("Humilde projeto desenvolvido por # Davi Resende #")
    print("                                 ################")
    input("Press <Enter> to continue.")
    print("\n"*50)
    numPart = int(input("Número de participantes do sorteio: "))
    cadastramento(numPart)
  
def cadastramento(x):
    nomes = []
    numPart = x
    i = 0
    for n in range(x):
        i += 1
        print("\n"*50)
        nome = input("Nome {}: ".format(i))
        nome = nome.upper()
        nomes.append(nome)
    main(nomes,numPart)
    
def main(nomes,x):
    main = {}
    exc = []
    z = randrange(x)
    i = 0
    while i < x:
        if z == i:
            z = randrange(x)
        elif z in exc:
            z = randrange(x)
        elif z != i and z not in exc:
            main[nomes[i]] = nomes[z]
            exc.append(z)
            i += 1
    print("\n"*50)
    print("Agora todos devem digitar seus nomes para verem com quem sairam.")
    input("Press <Enter> to continue.")
    print("\n" * 50)
    nome = input("Nome: ")
    nome = nome.upper()
    while True:
        try:
            if nome == "SAIR" or nome == "Sair" or nome == "sair":
                print("\n"*50)
                print("Programa Finalizado, espero que tenha ocorrido tudo certo!")
                break
            q = input("{} você saiu com: {}".format(nome,main[nome]))
            print("\n"*50)
            nome = input("Nome: ")
            nome = nome.upper()
        except:
            nome = input("Nome: ")
            nome = nome.upper()


inicio()

