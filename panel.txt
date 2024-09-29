import re 
import modulov2 as md2
print("\t","Automotora ruta 40")
print("\t","       Menu")
sw = 1
while sw == 1:
    print("1)Guardar")
    print("2)Buscar")
    print("3)Impresion de certificados")
    print("4)Salir")
    opc=int(input("Favor ingresar la digitar la opcion a realizar:"))
    if (opc > 0 and opc < 5):
      try:
        if opc == 1:
          print("1)Guardar")
          print("\t","Guardar datos de vehiculo")
          md2.Guardar()
          print(md2.matriz)
          continu=int(input("Desea salir 1=si o 2=no"))
          if continu == 1:
            md2.Salir()
            sw=0

        if opc == 2:
          print("2)Buscar") 
          md2.Buscar() 
          continu=int(input("Desea salir 1=si o 2=no"))
          if continu == 1:
            md2.Salir()
            sw=0  
  

        if opc == 3:
          print("3)Impresion de certificados")
          md2.Impres_d_certifi()
          continu=int(input("Desea salir 1=si o 2=no"))
          if continu == 1:
            md2.Salir()
            sw=0  
  

        if opc == 4: 
          md2.Salir()
          sw = 0
      except:
        print("Ingreso de opcion erroneo")