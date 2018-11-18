# Como configurar OpenCV External Modules o Contribution Modules en Android Studio para Windows de 64 bits

Configuración de OpenCV 3.4.2 (64 bits) y OpenCV_Cotrib 3.4.2 en Android Studio 3.1.4 (64 Bits) para Windows 7, 10 o más de 64 bits.

## Requerimientos:

- Primero deben de configurar el OpenCV (para Android) y el Android Studio como se muestra en este Link:
  https://github.com/yucaret/OpenCV-AndroidStudio/blob/master/README.md
- Descargar JDK, en mi caso yo estoy utilizando el "jdk-8u181-windows-x64.exe", pueden conseguir otras versiones en el link:
  https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
- Descargar el Apache Ant, en mi caso descargué el "apache-ant-1.10.5-bin.zip", lo pueden bajar del siguiente link:
  https://ant.apache.org/bindownload.cgi
- Decargar el CMAKE GUI, en mi caso descargué el "cmake-3.13.0-rc2-win64-x64.msi", lo pueden bajar del siguiente link:
  https://cmake.org/download/
- Descargar el MINGW, en mi caso descargué mingw-get-setup.exe, lo pueden bajar del siguiente link:
  https://osdn.net/projects/mingw/releases/
- Decargar el OpenCV (para windows, ojo), en mi caso descargué el "opencv-3.4.2-vc14_vc15.exe", lo pueden bajar del siguiente link:
  https://opencv.org/releases.html
- Decargar el OpenCV_Contrib (Extra Módulos), en mi caso descargué "opencv_contrib-3.4.2.zip", lo pueden bajar del siguiente link:
  
## Pasos:

- 1) La instalación y copia de archivos del OpenCV (Para Windows) y OpenCV_Contrib, debe de ser similar a lo siguiente, en mi caso yo coloqué ambos en la siguiente ruta "C:\OpenCV-android-sdk\opencv-342-win-sdk", similar a la siguiente imagen:

     ![image](https://user-images.githubusercontent.com/31372472/48667518-b8755200-eaa5-11e8-9e5f-e716128b9152.png)

     Los archivos instalados de OpenCV para windows quedan asi en la ruta "C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv-342-win-sdk".
     
     ![image](https://user-images.githubusercontent.com/31372472/48667544-5d902a80-eaa6-11e8-9733-e0204b1de47a.png)
     
     El OpenCV_Contrib queda así en la siguiente ruta "C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv_contrib-342-win".
     
     ![image](https://user-images.githubusercontent.com/31372472/48667548-8adcd880-eaa6-11e8-9e80-d6ea8e6e5813.png)

- 2) Configurar Variables de Entorno, después de instalar todo lo que se menciono líneas arriba, se debe de configurar algunas variables de entorno. En mi caso no tenia configurado el ANT_HOME y el JAVA_HOME

     ![image](https://user-images.githubusercontent.com/31372472/48667204-3aae4800-ea9f-11e8-9ab7-b9019156f0af.png)
     
     Tambien debes de configurar en el "path", el MINGW, Java Tools, SDK Tools, SDK Platform Tools, Java y Ant, luego dar Aceptar en todo.
     
     ![image](https://user-images.githubusercontent.com/31372472/48667235-c6c06f80-ea9f-11e8-99b8-9f4052c90aa3.png)

- 3) Configurar el JDK, para ello debes de primero abrir tu Android Studio, luego ingresar a File --> Project Structure, luego dar click  en "SDK Location" y en la sección de "JDK Location", quitar el check y colocar a ruta del JDK, en mi caso la ruta de mi sdk es:
     
     C:\Program Files\Java\jdk1.8.0_181
     
     La configuración debe de quedar como la siguiente imagen y darle "OK".
     
     ![image](https://user-images.githubusercontent.com/31372472/48667142-d6d74f80-ea9d-11e8-99e8-46874ce50331.png)
     
- 4) Configurar MinGW, abrir el "MinGW Installetion Manager", y en la sección de dar check, darle check a lo siguiente (tener en cuenta que el MinGW tiene configuraciones predefinidas y posiblemente algunos ya esten marcados):

     * mingw32-base
     * mingw32-binutils
     * mingw32-gcc
     * mingw32-gcc-core-deps
     * mingw32-gcc-g++
     * mingw32-gcc-gdb
     * mingw32-libatomic
     * mingw32-libgcc
     * mingw32-libgmp
     * mingw32-libgomp
     * mingw32-libgomp-deps
     * mingw32-libiconv
     * mingw32-libintl
     * mingw32-libisl
     * mingw32-libmingwex
     * mingw32-libmpc
     * mingw32-libmpfr
     * mingw32-libpthreadgc
     * mingw32-libquadmath
     * mingw32-libssp
     * mingw32-libstdc++
     * mingw32-libz
     * mingw32-make
     * mingw32-mingw-get
     * mingw32-mingwrt
     * mingw32-w32api
     * msys-base
     * msys-bash
     * msys-bzip2
     * msys-core
     * msys-coreutils
     * msys-diffutils
     * msys-dos2unix
     * msys-file
     * msys-findutils
     * msys-gawk
     * msys-grep
     * msys-gzip
     * msys-less
     * msys-libbz2
     * msys-libiconv
     * msys-libintl
     * msys-liblzma
     * msys-libmagic
     * msys-libregex
     * msys-libtermcap
     * msys-make
     * msys-sed
     * msys-tar
     * msys-termcap
     * msys-texinfo
     * msys-xz
     * msys-zlib
     
     Se ve similar a esta imagen (esta imagen no muestra todos los check que se menciona en la lista de arriba debido a la gran cantidad, pero podrán ver todas las imagenes en este link: XXXXXXXX).
     
     ![image](https://user-images.githubusercontent.com/31372472/48667459-1b65e980-eaa4-11e8-8147-64d1f83c296e.png)
     
- 5) A partir de aquí empezamos a construir los archivos de OpenCV de Windows y OpenCV_Contrib para que luego sean utilizados por el OpenCV para Andorid, para ello abrimos el CMAKE, allí colocamos las rutas de la fuente y de la construcción, en micaso las rutas son:

     Source: C:/OpenCV-android-sdk/opencv-342-win-sdk/opencv-342-win-sdk/sources
     Build: C:/OpenCV-android-sdk/opencv-342-win-sdk/opencv-342-win-sdk/build
     
     Y se deben de ver como la siguiente imagen:
     
     ![image](https://user-images.githubusercontent.com/31372472/48668451-e1a0dd00-eabb-11e8-8eb7-30f051a30750.png)
     
- 6) Luego apretamos el botón "Configure", inmediatamente aparecera otra pantalla donde debemos especificar el "Generador" el cual debemos elegir "MinGW Makefiles", y despues seleccionamos "Specify toolchain file for cross-compiling", similar a como se ve en la imagen siguiente:

![image](https://user-images.githubusercontent.com/31372472/48668494-bd91cb80-eabc-11e8-89f3-8a93ea084d6c.png)


     
