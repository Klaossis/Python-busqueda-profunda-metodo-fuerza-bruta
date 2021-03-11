# GRAFO 2 DE BUSQUEDA COMPLETA
import sys

# diccionario = {"nodo" : "A", "distacian": "21"}

contcaminos = 0
temp = 0
cont3 = 0
cont2 = 0
cont1 = 0 #cont1 determina el nodo actualmente ubicado
tamano = 0
next = ""
bandera = 0
banderab = 0
banderad = 0
bandera1 = 0
valornext = 999
paso = ""
anterior = ""
anterior2 = ""
inicial = ""
final = ""
act = ""
opt = 0
costo = 0

caminos = [[0],[0],[0],[0]]
caminosfi = []
#caminos = []
ruta = []
nodos = [["a", "b", 3, "h", 12],
         ["b", "a", 3, "e", 6, "d", 4, "f", 5],
         ["c", "f", 2, "g", 3, "d", 9],
         ["d", "b", 4, "c", 9, "i", 5, "h", 25],
         ["e", "b", 6, "f", 1],
         ["f", "e", 1, "b", 5, "c", 2],
         ["g", "c", 3, "j", 7],
         ["h", "a", 12, "d", 25, "i", 1],
         ["i", "j", 3, "d", 5, "h", 1],
         ["j", "i", 3, "g", 7]]


def imprimir():
    cont = 0;
    for x in nodos:
        print(nodos[cont][0])
        cont += 1


def busqueda():
    global inicial
    global final
    global next
    imprimir()
    print("Selecione el nodo inicial:")
    inicial = input()
    print("Selecione el nodo a buscar")
    final = input()
    next = inicial
    ubicar()


def ubicar():
    # Acomoda el nodo actual al nuevo
    # coloca paso en el nodo buscado guardada su ubicacion en cont1
    global anterior
    global cont1
    global next
    global bandera1
    global paso
    global nodos
    if bandera1 == 1: #genera un anterior para ni visitarlo inutil
        anterior = paso
    bandera1 = 1
    cont1 = 0
    while nodos[cont1][0] != next:
        cont1 += 1
    paso = nodos[cont1][0]
    ruta.append(nodos[cont1][0])
    #temportal = nodos[cont1][0]
    #print(nodos[cont1][0])
    #caminos[contcaminos].append(temportal)
    caminos[contcaminos].append(nodos[cont1][0])
    if paso == final:
        print("!Nodo encontrado!")
        print("El camino costo =", costo)
        print("La ruta fue: ", ruta)
        salir()
    else:
        selecionar2()

def selecionar2():
    global inicial
    global cont1
    global cont2
    global cont3
    global banderab
    global banderad
    global temp
    global costo
    global valornext
    global next
    global paso
    global nodos
    global anterior2
    global contcaminos
    global tamano
    aux = 0
    aux2 = 0
    aux3 = 0
    banfi = ""
    tamcaminos = 0
    valornext = 999
    cont2 = 1
    cont3 = 1
    temp = 0
    salsa = 0
    camcont = 0
    temp3 = ""
    temp2 = 0
    bandera = 0
    #caminos.append(nodos[cont1][0])
    #if len(nodos[cont1]) == 9:
    #    caminos.append()
    salsa = len(caminos[contcaminos])
    salsa -=1
    print(caminos)
    tamcaminos = len(nodos[cont1])
    #print(banderab)
    #print(banderad)
    #if caminos[contcaminos][salsa] == "b":
    #    if banderab == 1:
    #        tamcaminos -= 2
    #    if banderab == 2:
    #        tamcaminos -= 4
    #if caminos[contcaminos][salsa] == "d":
    #    if banderad == 1:
    #        tamcaminos -= 2
    #    if banderad == 2:
    #        tamcaminos -=4
    if tamano > 0:
        tamcaminos = tamano
    print("tamcaminos: ",tamcaminos)
    print("nodo actual", nodos[cont1][0])
    print("inicial: ", inicial)
    if nodos[cont1][0] == inicial and tamcaminos == 1:
        print("carambola")
        final1()


    while cont3 < tamcaminos: #and bandera == 0: # guarda el nodo siguiente en temp
        #print("len",len(nodos[cont1]))
        #print(cont3)
        #print("nodo",nodos[cont1][cont3])
        temp3 = nodos[cont1][cont3]
        print("temp3: ",temp3)
        #temp3 = nodos[cont1][cont3]
        #if bandera == 0
        cont2 = 1
        #print("cont2: ",cont2)
        #print("caminos tama",len(caminos[contcaminos]))
        #aux = 0
        if anterior2 == temp3:
            print("aux3")
            aux3 = 1


        while cont2 < len(caminos[contcaminos]) and aux3 == 0: #and bandera == 0: #compara si el sig nodo es viable
            aux +=1
            #print("len camino",len(caminos[contcaminos]))
            #print("cont2", cont2)
            print("temp3",temp3)
            print("camino",caminos[contcaminos][cont2])
            if temp3 != caminos[contcaminos][cont2]:
                aux2 += 1
                #banfi = temp3
                cont2 += 1
            else: cont2 += 1
        if cont2 >= len(caminos[contcaminos]):
            bandera = 1
            #temp3 =
            #cont2 += 1
        print("aux2: ", aux2)
        print("aux: ", aux)
        if aux2 == aux and aux3 == 0:
            banfi = temp3
        print("banfi: ", banfi)
        print("anterior: ",anterior2)
        aux = 0
        aux2 = 0
        aux3 = 0
        cont3 += 2
        print("len2",len(nodos[cont1]))
        print(cont3)
    tamano = 0
    anterior2 = ""
    if banfi == "":
        salir()
    next = banfi
    #next = temp3
    print("next: ",next)
    ubicar()



    #   if temp < valornext and temp > 0:
    #       if nodos[cont1][cont2 - 1] != anterior:
    #          valornext = temp
    #          temp2 = cont2
    #  cont2 += 2
    #cont2 = temp - 1
    #cont2 = temp2 - 1



    #while cont3 <= len(nodos[cont1]):
    #    temp3 = nodos[cont1][cont3]
    #    while salsa <= len(caminos[camcont])
    #        if

    #while cont2 <= len(nodos[cont1]):
    #    temp = nodos[cont1][cont2]
    #    while temp




    #while cont2 <= len(nodos[cont1]):
    #    temp = nodos[cont1][cont2]
    #    if temp < valornext and temp > 0:
    #        if nodos[cont1][cont2 - 1] != anterior:
    #            valornext = temp
    #            temp2 = cont2
    #    cont2 += 2
    #cont2 = temp - 1
    #cont2 = temp2 - 1
    #costo = costo + valornext
    #next = nodos[cont1][cont2]
    #if costo > 300:
    #    imposible()
    #ubicar()

def selecionar():
    # seleciona el nuevo nodo actual
    # inicia la busqueda del nodo de menor costo
    global cont1
    global cont2
    global temp
    global costo
    global valornext
    global next
    global paso
    global nodos
    valornext = 999
    cont2 = 2
    temp = 0
    temp2 = 0
    # print("calambora")
    # print(paso)
    while cont2 <= len(nodos[cont1]):
        temp = nodos[cont1][cont2]
        # print("temp",temp,valornext)

        if temp < valornext and temp > 0:
            # print("valor next ", valornext, temp)
            # print("valor actual", nodos[cont1][cont2-1], anterior)
            if nodos[cont1][cont2 - 1] != anterior:
                valornext = temp
                # print("salsa")
                temp2 = cont2
            # print("temp2",temp2)
            # print("valor next ", valornext)
        cont2 += 2
        # print(nodos[cont1][cont2-3])
    cont2 = temp - 1
    cont2 = temp2 - 1
    costo = costo + valornext
    # print(nodos[cont1][cont2 - 1])
    # print("ulti")
    # print(nodos[cont1][0])
    # print(paso)
    next = nodos[cont1][cont2]
    # print("anterior", anterior)
    # print("next", next)
    if costo > 300:
        imposible()
    ubicar()

def salir():
    global contcaminos
    global anterior2
    global tamano
    global banderad
    global banderab
    global inicial
    global next
    global act
    global nodos
    print("salsa")
    extraido = ""
    cantidad = ""
    tamano = 0
    tiempo = 0
    tiempo2 = 0
    auxiliar = 0
    auxiliar2 = ""
    caminos.append([0])
    temp = contcaminos
    temp += 1
    caminos[temp] = caminos[contcaminos].copy()
    anterior2 = caminos[temp].pop()
    contcaminos +=1
    auxiliar = len(caminos[contcaminos])
    auxiliar -=1
    auxiliar2 = caminos[contcaminos][auxiliar]


    extraido = auxiliar2 # ubicacion actual c
    while nodos[tiempo][0] != extraido: # se coloca en C
        tiempo += 1
    #tamano = len(nodos[tiempo])
    #tamano -= 1
    while nodos[tiempo][tiempo2] != anterior2: # encuentra ubicacion de g
        tiempo2 += 1
    tamano = tiempo2

    if anterior2 == inicial:
        valor()
    if anterior2 == "b":
        banderab += 1
    if anterior2 == "d":
        banderad += 1
    act = auxiliar2
    #next = anterior2
    #ubicar()
    mover()
    #selecionar2()

def valor():
    global caminosfi
    global nodos
    bandera = 0
    a = 0
    b = 0
    c = 0
    aux = 0
    aux2 = 0
    d = 0
    b = len(caminosfi)
    letracam = 1
    tamcam = 0
    print("caramalino elegante")
    while a < b:
        print(caminosfi)
        print("carton")
        tamcam = len(caminosfi[a])
        tamcam -=1
        print(nodos[c][0])
        #print(caminosfi[a][letracam+1])
        c = 0
        while nodos[c][0] != caminosfi[a][letracam] and letracam < tamcam:
            print("cordillera: ",nodos[c][0] )
            print("colina: ",caminosfi[a][letracam+1])
            c += 1
        d = 0
        print("nodo", nodos[c][d])
        while nodos[c][d] != caminosfi[a][letracam+1]:
            print("nodo",nodos[c][d])
            print(caminosfi[a][letracam+1])
            d += 1
        print("cordero")
        aux = caminosfi[a][0]
        aux2 = nodos[c][d+1]
        aux = aux + aux2
        caminosfi[a][0] = aux
        letracam += 1
        if letracam == tamcam:
            letracam = 1
            a += 1
    print("coral")
    mostrarfinal()
    #print(caminosfi)
    sys.exit(0)


def mover():
    global anterior
    global cont1
    global next
    global bandera1
    global paso
    global nodos
    global act
    #if bandera1 == 1: #genera un anterior para ni visitarlo inutil
    #    anterior = paso
    #bandera1 = 1
    print("act: ",act)
    print("patata")
    cont1 = 0
    while nodos[cont1][0] != act:
        cont1 += 1
    #paso = nodos[cont1][0]
    #ruta.append(nodos[cont1][0])
    #temportal = nodos[cont1][0]
    #print(nodos[cont1][0])
    #caminos[contcaminos].append(temportal)
    #caminos[contcaminos].append(nodos[cont1][0])
    #if paso == final:
    #    print("!Nodo encontrado!")
    #    print("El camino costo =", costo)
    #    print("La ruta fue: ", ruta)
    #    salir()
    #else:
    #    selecionar2()
    selecionar2()


def final1():
    global caminos
    global caminosfi
    global final
    print("felicidades")
    a = 0
    b = 0
    c = 0
    d = 0
    a = len(caminos)
    while b < a:
        c = len(caminos[b])
        c -=1
        if caminos[b][c] == final:
            caminosfi.append([0])
            caminosfi[d] = caminos[b].copy()
            d += 1
        b += 1
    print(caminosfi)
    print("Cantidad de caminos posibles: ",d)
    valor()
    sys.exit(0)

def mostrarfinal():
    global caminosfi
    temportal = 99999
    a = 0
    b = 0
    tam = 0
    tam = len(caminosfi)
    while a < tam:
        if caminosfi[a][0] < temportal and caminosfi[a][0] > 0:
            temportal = caminosfi[a][0]
            b = a
        a += 1
    print("el mejor camino es :", caminosfi[b])
    print("sardinas saltarinas")

    print("1.- Mostrar todos los caminos")

    optc = input()
    if optc == "1":
        for x in range(len(caminosfi)):
            print(caminosfi[x])
    sys.exit(0)



def imposible():
    print("Debido al metodo codicioso es imposible llegar al nodo objetivo :c")
    print("emoji de gato triste")
    sys.exit(0)


print("1.- Buscar nodo")
print(len(nodos))
print(len(nodos[1]))
# print(len(nodos[0]))
# print("2.- Agregar nodo")
# print("3.- Editar nodo")
opt = input()
if opt == "1":
    busqueda()

# buenos dias mundo
