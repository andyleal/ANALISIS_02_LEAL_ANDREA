# ANALISIS_02_LEAL_ANDREA
# -*- coding: utf-8 -*-

import csv 
totales = []

with open("synergy_logistics_database.csv", "r") as archivo_csv:
     lector = csv.reader(archivo_csv)
    #lector = csv.DictReader(archivo_csv)
    

#valor de las exportaciones
     for linea in lector:
         #if linea[2] == "imports":
             #continue
         #elif linea[9] == "total_value":
             #continue
             totales.append(linea)
             print(linea)
             
direccion = "Exports"
contador = 0
rutas_contadas = []
conteo_rutas = []
#conteo_rutas = 15408

for ruta in totales:
    
    if ruta[1] == direccion:
        print(ruta)
        contador +=1
        
    if ruta [1] == direccion: 
        ruta_actual = [ruta [2], ruta [3]]
        
        if ruta_actual not in rutas_contadas:
            for viaje in totales:
                if ruta_actual == [viaje [2], viaje [3]]:
                    contador += 1

#Numero de rutas contadas : 144                    
        rutas_contadas.append(ruta_actual)
        conteo_rutas.append([ruta[2], ruta [3], contador])
        contador = (0)


                 
        
    

