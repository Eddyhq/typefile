# typefile
#!/usr/bin/env python3
# Eddy Hoxsas

import os
import sys

if len(sys.argv) < 2:
    print("Uso: python TypeFile.py <nombre_archivo>")
    sys.exit(1)
    
archivo = sys.argv[1]

# Limpiar pantalla
os.system('cls' if os.name == 'nt' else 'clear')

def mostrar_archivo_con_lineas(archivo):
    try:
        with open(archivo, 'r', encoding='utf-8') as file:
            for numero, linea in enumerate(file, start=1):
                print(f"{numero:4}: {linea.rstrip()}")
    except FileNotFoundError:
        print(f"Error: El archivo '{archivo}' no existe.")
    except Exception as e:
        print(f"Ocurrió un error: {e}")

# Mostrar contenido numerado
mostrar_archivo_con_lineas(archivo)
