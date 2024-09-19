
1. du -a /home | sort -n -r | head -n:

du -a /home: Muestra el tamaño de todos los archivos y directorios dentro de /home, incluyendo archivos individuales.
sort -n -r: Ordena los resultados numéricamente (-n) de mayor a menor (-r).
head -n: Muestra solo las primeras n líneas del resultado, pero falta especificar el número de líneas, lo que parece un error en el comando. Debería ser algo como head -n 10 para mostrar los 10 archivos o directorios más grandes.

2. du -a | sort -n -r | head -n 10:

du -a: Muestra el tamaño de todos los archivos y directorios en el directorio actual.
sort -n -r: Ordena el resultado por tamaño, de mayor a menor.
head -n 10: Muestra los 10 archivos o directorios más grandes.

3. du -hs * | sort -rh | head -7:

du -hs *: Muestra el tamaño de cada archivo o directorio en el directorio actual, con formato legible (-h), pero sin desglosar su contenido (-s).
sort -rh: Ordena los resultados en orden descendente por tamaño.
head -7: Muestra los 7 archivos o directorios más grandes.

4. du -Sh | sort -rh | head -7:

du -Sh: Muestra el tamaño de los archivos y directorios, pero sin incluir los subdirectorios (-S), y con formato legible.
sort -rh: Ordena por tamaño de mayor a menor.
head -7: Muestra los 7 archivos o directorios más grandes.

5. find -type f -exec du -Sh {} + | sort -rh | head -n 8:

find -type f: Encuentra todos los archivos en el directorio actual y sus subdirectorios.
-exec du -Sh {} +: Para cada archivo encontrado, ejecuta du -Sh para mostrar su tamaño en formato legible.
sort -rh: Ordena los archivos por tamaño, de mayor a menor.
head -n 8: Muestra los 8 archivos más grandes.

6. find /home/tiago/Downloads -type f -exec du -Sh {} + | sort -rh | head -n 2:

find /home/tiago/Downloads -type f: Encuentra todos los archivos dentro del directorio /home/tiago/Downloads.
-exec du -Sh {} +: Ejecuta du -Sh para obtener el tamaño de cada archivo.
sort -rh: Ordena los archivos por tamaño, de mayor a menor.
head -n 2: Muestra los 2 archivos más grandes en ese directorio.


















