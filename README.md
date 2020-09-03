# Reporte 01-Aguirre_Diana

from lifestore_file import lifestore_searches
from lifestore_file import lifestore_sales
from lifestore_file import lifestore_products
#usuario = store
#contraseña = life

print("Bienvenido a Lifestore")
print("Para poder comenzar es necesario ingresar con un usuario y constraseña") #Bienvenida al programa de lifestore 

usuario = input("Ingresa el nombre de usuario  ")

usuario_correcto=0
while usuario_correcto != 1:
  if usuario == "store" :
    print("Usuario correcto")
    usuario_correcto=1
  else:
    print("Usuario invalido, por favor intente otra vez")
    usuario=input("Ingresa el nombre de usuario ") #Se le pide el nombre de usuario en donde en caso de ser incorrecta se repite el ciclo hasta que sea correcto.

contraseña = input ("Ingresa la contraseña  ")

password=0

while password !=1 :
  if contraseña == "life" :
    print("Contraseña correcta")
    password=1
  else:
    print("Contraseña incorrecta por favor intente otra vez")
    contraseña=input ("Ingrese la contraseña  ")#Se le pide la contraseña al usuario en donde en caso de ser incorrecta se repite el ciclo hasta que se ingrese la contraseña correcta.


contador=0
total_sales= []

for producto in lifestore_products:
  for sale in lifestore_sales:
    if producto[0]==sale[1]:
      contador +=1
  formato_ideal=[producto[0],producto[1],contador]
  total_sales.append(formato_ideal)
  contador=0 #Se crea un bucle con una lista en donde se van sumando el número de veces que aparece un item en una lista


contadorb = 0
total_busqueda= []

for product in lifestore_products:
  for search in lifestore_searches:
    if product[0]==search[1]:
      contadorb += 1
  formato_search=[product[0],product[1],contadorb]
  total_busqueda.append(formato_search)
  contadorb=0 #Se crea un bucle con una lista en donde se van sumando el número de veces que aparece un item en una lista

mayores_ventas = []
menores_ventas = []
mayores_busquedas = []
menores_busquedas = []

maximo=total_sales[0][2]
minimo=total_sales[0][2]

maximob=total_busqueda[0][2]
minimob=total_busqueda[0][2]

for ventas in total_sales:
  if maximo <= ventas [2]:
    mayores_ventas.append(ventas)
    maximo=ventas[2] #Se crear una nueva lista en donde se van comparando el numero de veces que aparece un elemnto en la lista creada con anterioridad, si es mayor se agrega a la lista y si no sigue bsucando elementos.

   
for ventas in total_sales:
  if minimo >= ventas [2]:
    menores_ventas.append(ventas)
    minimo=ventas[2]  #Se crear una nueva lista en donde se van comparando el numero de veces que aparece un elemnto en la lista creada con anterioridad, si es menor se agrega a la lista y si no sigue bsucando elementos.


for busqueda in total_busqueda:
  if maximob <= busqueda [2]:
    mayores_busquedas.append(busqueda)
    maximob=busqueda[2]#Se crear una nueva lista en donde se van comparando el numero de veces que aparece un elemnto en la lista creada con anterioridad, si es mayor se agrega a la lista y si no sigue bsucando elementos

   
for busqueda in total_sales:
  if minimob >= busqueda [2]:
    menores_busquedas.append(ventas)
    minimob =busqueda[2] #Se crear una nueva lista en donde se van comparando el numero de veces que aparece un elemnto en la lista creada con anterioridad, si es menor se agrega a la lista y si no sigue bsucando elementos.


correcta = 0

while correcta != "1" :
  print('Bienvenido elige una opción \n 1. Productos con mayores ventas \n 2. Prodcutos con menores ventas \n 3. Productos con mayores busquedas \n 4. Productos con menores busquedas \n 5. Ingresos' ) #Menú de opciones en donde se selecciona que opción quiere elegir el usuario
  opcion_seleccionada=input("Escribe la opción seleccionada    ")
  if opcion_seleccionada == "1" :
    print( "Has seleccionado la opción 1")
    for mayores in mayores_ventas:
      print("El producto",mayores[1],"se vendió",mayores[2],"veces")
    correcta = input("Para salir presione 1, si no es asi presione 2  ")
  elif opcion_seleccionada == "2" :
    print ("Has seleccionado la opción 2")
    for menores in menores_ventas:
      print("El producto", menores[1],"se vendió",menores[2],"veces")
    correcta = input("Para salir presione 1, si no es asi presione 2  ")
  elif opcion_seleccionada == "3" :
    print ("Has seleccionado la opción 3")
    for mayores in mayores_busquedas:
      print("El producto",mayores[1],"se buscó",mayores[2],"veces")
    correcta = input("Para salir presione 1, si no es asi presione 2  ") 
  elif opcion_seleccionada == "4" :
    print ("Has seleccionado la opción 4")
    for menores in menores_busquedas:
      print("El producto", menores[1] ,"se buscó", menores[2], "veces")
    correcta = input("Para salir presione 1, si no es asi presione 2  ")
  elif opcion_seleccionada == "5" :
    print ("Has seleccionado la opción 5")
    print("Por el momento no puedo proporcionar la información solicitada")
    correcta = input("Para salir presione 1, si no es asi presione 2  ")
  else: 
    print("Opción incorrecta, por favor elige una opción del menú")
    correcta=0 #Dependiendo la opción seleccionada aparece la leyenda, en caso de que no se seleccione una opción correcta se repite el ciclo)


print("Esperamos que la información proporcionada sea de utilidad")
print("Hasta Luego")    
