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
     
- 6) Luego apretamos el botón "Configure", inmediatamente aparecera otra pantalla donde debemos especificar el "Generador" el cual debemos elegir "MinGW Makefiles", y despues seleccionamos "Specify toolchain file for cross-compiling" y apretamos "Next".

     ![image](https://user-images.githubusercontent.com/31372472/48668494-bd91cb80-eabc-11e8-89f3-8a93ea084d6c.png)
     
     Seleccionamosel archivo que se encuentra dentro del mismo OpenCV para windows, en mi caso en la siguiente ruta:
     
     C:/OpenCV-android-sdk/opencv-342-win-sdk/opencv-342-win-sdk/sources/platforms/android/android.toolchain.cmake
     
     Se debe de ver como la siguiente imagen y luego apretamos "Finish".
     
     ![image](https://user-images.githubusercontent.com/31372472/48668530-a1425e80-eabd-11e8-8194-4513d11de5f3.png)
     
     Inmeditamete se generará un error que luego en los siguientes pasos se solucionará, solo darle "OK".
     
     ![image](https://user-images.githubusercontent.com/31372472/48668552-1dd53d00-eabe-11e8-849f-9a640325cfb2.png)
     
     El error que se genera es el siguiente:
     
      CMake Error at platforms/android/android.toolchain.cmake:458 (message):
         Could not find neither Android NDK nor Android standalone toolchain.

         You should either set an environment variable:
              export ANDROID_NDK=~/my-android-ndk
         or
              export ANDROID_STANDALONE_TOOLCHAIN=~/my-android-toolchain
         or put the toolchain or NDK in the default path:
              sudo ln -s ~/my-android-ndk C:/Program Files/android-ndk
              sudo ln -s ~/my-android-toolchain /opt/android-toolchain

      Call Stack (most recent call first):
         C:/Program Files/CMake/share/cmake-3.13/Modules/CMakeDetermineSystem.cmake:94 (include)
      CMakeLists.txt:127 (project)
      
      CMake Error: CMAKE_CXX_COMPILER not set, after EnableLanguage
      CMake Error: CMAKE_C_COMPILER not set, after EnableLanguage
      
      Configuring incomplete, errors occurred!

- 7) En estos siguientes pasos vamos a estar modificando la sección de configuraciones y cambiamos variable:

     - a) Comenzamos cambiando la variable CMAKE_MAKE_PROGRAM por el siguiente programa de construcción que se encuentra en nuestro NDK, en mi caso se encuentra en la siguiente ruta:
     
     C:\android-ndk-r16b\prebuilt\windows-x86_64\bin\make.exe
     
     En imagen se debe de ver así:
     
     ![image](https://user-images.githubusercontent.com/31372472/48672340-a4ac0900-eb02-11e8-83f9-76f24f57ed26.png)

     - b) Ahora, como se indica en el error, agregamos el NDK, que en mi caso se encuentra en la ruta "C:/android-ndk-r16b", para ello vamos al botón "Add Entry", colocamos como nombre de la variable "ANDROID_NDK", el tipo "Path" y el valor la ruta del ndk, como se ve en la imagen.
     
     ![image](https://user-images.githubusercontent.com/31372472/48676583-ab547380-eb36-11e8-9277-07325e65cc52.png)

     - c) A continuación debemos de configurar el nombre de carpeta donde se encuentra la copia de los sistemas raíz de la plataforma que queremos compilar, en este caso el nombre es "arm-linux-androideabi-4.9" y se encuentra dentro de la ruta "C:\android-ndk-r16b\toolchains"; similar al paso b, ingresamos a "Add Entry", colocamos como nombre de la variable "ANDROID_TOOLCHAIN_NAME", el tipo "String" y el valor "arm-linux-androideabi-4.9", como se ve en la imagen.
     
     ![image](https://user-images.githubusercontent.com/31372472/48676733-eeafe180-eb38-11e8-8a16-2abad4732d58.png)
     
     - d) Tambien debemos configurar la ruta del JDK que se encuentra dentro de la ruta "C:\Program Files\Java\jdk1.8.0_181"; similar al paso b, ingresamos a "Add Entry", colocamos como nombre de la variable "JAVA_HOME", el tipo "Path" y el valor "C:\Program Files\Java\jdk1.8.0_181", como se ve en la imagen.
     
     ![image](https://user-images.githubusercontent.com/31372472/48677108-0178e500-eb3e-11e8-8b26-b34e0f561473.png)
