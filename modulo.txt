#def nano1 ():
#   nano=input("Favor ingresar el dato:")
import re
import numpy as np

nom=['Tipo','Marca','Patente','Modelo','Precio','Multas','F.d.regitr','N.dueño']
nom2=['Tipo','Marca','Patente','Modelo','Precio','Multas','F.d.regitr','N.dueño','Certificados de gases','Anotaciones Vigentes']

tip=["VANS"]
mar=["VOLVO"]
pat=['AAAA11']
mod=["Charizard"]
pre=['95000000']
mul=[('2300'),('5400'),('3700'),('4850')]
freg=['05/06/2024']
ndu=['Pablo Cardenas']
cert_c=[['Alta']]
anot_vi=[['Vehiculo con luz delantera dañada']]

matriz1 = [[tip],[mar],[pat],[mod],[pre],[mul],[freg],[ndu]]
matriz2 = [[tip],[mar],[pat],[mod],[pre],[mul],[freg],[ndu],[cert_c],[anot_vi]]

def Guardar():
    while True:
        ndtip = input("Tipo de vehículo (AUTO, SVVS, PICKUPS o VANS): ").upper()
        if ndtip in ["AUTO", "SVVS", "PICKUPS", "VANS"]:
            tip.append(ndtip)
            break
        else:
            print("Tipo de vehículo inválido. Intente nuevamente.")

    while True:
        ndmar = input("Marca del vehículo: ")
        if 2 <= len(ndmar) <= 12:
            mar.append(ndmar)
            break
        else:
            print("Marca inválida (debe tener entre 2 y 12 caracteres). Intente nuevamente.")

    while True:
        ndpat = input("Patente del vehículo: ")
        if re.match(r"^[A-Z]{4}[0-9]{2,3}$", ndpat):
            pat.append(ndpat)
            break
        else:
            print("Patente inválida. Intente nuevamente.")
    ##Modelo        
    ndmod=input(f"Modelo de vehiculo:")
    mod.append(ndmod)
    ##Precio
    while True:
        ndpre=int(input(f"Precio de vehiculo:"))
        if ndpre > 6880000:
            pre.append(ndpre)
            print("Registro guardado")
            break
        else:
            print("El precio debe ser mayor a 6,880,000. Intente nuevamente.")
            print("Precio válido:", pre) 


def Buscar():
    print("\t","Buscar vehiculo")
    soli2=input("Favor indicar la patente del vehiculo a consultar:")
    if soli2 in pat:
        print("Patente encontrada")
        for i, sublista in enumerate(matriz1):
            try:
                posicion = sublista.index(pat)
                pos= int(posicion)
                for l1, l2 in zip(nom, matriz1):
                    print(l1,l2[pos])     
                break 
            except ValueError:
                pass  
    else:
        print("patente no encontrada, favor ingresar una patente valida")
        print("Formato de patente AA0000 O AAAA00")

def Impres_d_certifi():
    print("\t","Buscar vehiculo")
    soli2=input("Favor indicar la patente del vehiculo a consultar:")
    if soli2 in pat:
        print("Patente encontrada")
        for i, sublista in enumerate(matriz2):
            try:
                posicion = sublista.index(pat)
                pos= int(posicion)
                print("Certificador de Automovil",{soli2})
                for l1, l2 in zip(nom2, matriz2):
                    print(l1,l2[pos])     
                break 
            except ValueError:
                pass  
    else:
        print("patente no encontrada, favor ingresar una patente valida")
        print("Formato de patente AA0000 O AAAA00")


def Salir():
    print("Muchas gracias, por ocupar el programa")
    print("\t","Claudio Vasquez-V1.00")



