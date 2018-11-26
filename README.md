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

     Los archivos instalados de OpenCV para windows quedan así en la ruta "C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv-342-win-sdk".
     
     ![image](https://user-images.githubusercontent.com/31372472/48667544-5d902a80-eaa6-11e8-9733-e0204b1de47a.png)
     
     El OpenCV_Contrib queda así en la siguiente ruta "C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv_contrib-342-win".
     
     ![image](https://user-images.githubusercontent.com/31372472/48667548-8adcd880-eaa6-11e8-9e80-d6ea8e6e5813.png)

- 2) Configurar Variables de Entorno, después de instalar todo lo que se mencionó líneas arriba, se debe de configurar algunas variables de entorno. En mi caso no tenía configurado el ANT_HOME y el JAVA_HOME

     ![image](https://user-images.githubusercontent.com/31372472/48667204-3aae4800-ea9f-11e8-9ab7-b9019156f0af.png)
     
     También debes de configurar en el "path", el MINGW, Java Tools, SDK Tools, SDK Platform Tools, Java y Ant, luego dar Aceptar en todo.
     
     ![image](https://user-images.githubusercontent.com/31372472/48667235-c6c06f80-ea9f-11e8-99b8-9f4052c90aa3.png)

- 3) Configurar el JDK, para ello debes de primero abrir tu Android Studio, luego ingresar a File --> Project Structure, luego dar click  en "SDK Location" y en la sección de "JDK Location", quitar el check y colocar a ruta del JDK, en mi caso la ruta de mi sdk es:
     
     C:\Program Files\Java\jdk1.8.0_181
     
     La configuración debe de quedar como la siguiente imagen y darle "OK".
     
     ![image](https://user-images.githubusercontent.com/31372472/48667142-d6d74f80-ea9d-11e8-99e8-46874ce50331.png)
     
- 4) Configurar MinGW, abrir el "MinGW Installetion Manager", y en la sección de dar check, darle check a lo siguiente (tener en cuenta que el MinGW tiene configuraciones predefinidas y posiblemente algunos ya estén marcados):

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
     
     Se ve similar a esta imagen (esta imagen no muestra todos los check que se menciona en la lista de arriba debido a la gran cantidad, pero podrán ver todas las imágenes en este link: XXXXXXXXpendienteXXXXXXXX).
     
     ![image](https://user-images.githubusercontent.com/31372472/48667459-1b65e980-eaa4-11e8-8147-64d1f83c296e.png)
     
- 5) A partir de aquí empezamos a construir los archivos de OpenCV de Windows y OpenCV_Contrib para que luego sean utilizados por el OpenCV para Andorid, para ello abrimos el CMAKE, allí colocamos las rutas de la fuente y de la construcción, en mi caso las rutas son:

     Source: C:/OpenCV-android-sdk/opencv-342-win-sdk/opencv-342-win-sdk/sources
     Build: C:/OpenCV-android-sdk/opencv-342-win-sdk/opencv-342-win-sdk/build
     
     Y se deben de ver como la siguiente imagen:
     
     ![image](https://user-images.githubusercontent.com/31372472/48668451-e1a0dd00-eabb-11e8-8eb7-30f051a30750.png)
     
- 6) Luego apretamos el botón "Configure", inmediatamente aparecerá otra pantalla donde debemos especificar el "Generador" el cual debemos elegir "MinGW Makefiles", y después seleccionamos "Specify toolchain file for cross-compiling" y apretamos "Next".

     ![image](https://user-images.githubusercontent.com/31372472/48668494-bd91cb80-eabc-11e8-89f3-8a93ea084d6c.png)
     
     Seleccionamos el archivo que se encuentra dentro del mismo OpenCV para windows, en mi caso en la siguiente ruta:
     
     C:/OpenCV-android-sdk/opencv-342-win-sdk/opencv-342-win-sdk/sources/platforms/android/android.toolchain.cmake
     
     Se debe de ver como la siguiente imagen y luego apretamos "Finish".
     
     ![image](https://user-images.githubusercontent.com/31372472/48668530-a1425e80-eabd-11e8-8194-4513d11de5f3.png)
     
     Inmediatamente se generará un error que luego en los siguientes pasos se solucionará, solo darle "OK".
     
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

     - b) Ahora, como se indica en el error, agregamos el NDK, que en mi caso se encuentra, en mi caso, en la ruta "C:/android-ndk-r16b", para ello vamos al botón "Add Entry", colocamos como nombre de la variable "ANDROID_NDK", el tipo "Path" y el valor la ruta del ndk, como se ve en la imagen.
     
     ![image](https://user-images.githubusercontent.com/31372472/48676583-ab547380-eb36-11e8-9277-07325e65cc52.png)

     - c) A continuación debemos de configurar el nombre de carpeta donde se encuentra la copia de los sistemas raíz de la plataforma que queremos compilar, en este caso el nombre es "arm-linux-androideabi-4.9" y se encuentra, en mi caso, dentro de la ruta "C:\android-ndk-r16b\toolchains"; similar al paso b, ingresamos a "Add Entry", colocamos como nombre de la variable "ANDROID_TOOLCHAIN_NAME", el tipo "String" y el valor "arm-linux-androideabi-4.9", como se ve en la imagen.
     
     ![image](https://user-images.githubusercontent.com/31372472/48676733-eeafe180-eb38-11e8-8a16-2abad4732d58.png)
     
     - d) También debemos configurar la ruta del JDK que se encuentra, en mi caso, dentro de la ruta "C:/Program Files/Java/jdk1.8.0_181"; similar al paso b, ingresamos a "Add Entry", colocamos como nombre de la variable "JAVA_HOME", el tipo "Path" y el valor "C:\Program Files\Java\jdk1.8.0_181", como se ve en la imagen.
     
     ![image](https://user-images.githubusercontent.com/31372472/48677108-0178e500-eb3e-11e8-8b26-b34e0f561473.png)

     - e) También debemos configurar la ruta del ANT que se encuentra, en mi caso, dentro de la ruta "C:/apache-ant-1.10.5/bin/ant.bat"; similar al paso b, ingresamos a "Add Entry", colocamos como nombre de la variable "ANT_EXECUTABLE", el tipo "Filepath" y el valor mencionado inicialmente, como se ve en la imagen.
     
     ![image](https://user-images.githubusercontent.com/31372472/48677717-f5455580-eb46-11e8-8643-18011f728623.png)

     - f) Por ultimo configuramos el SDK, para ello vamos a tener que configurar 3 variables, primero la ruta del SDK, en mi caso se encuentra en la ruta "C:/Users/win/AppData/Local/Android/Sdk"; similar al paso b, ingresamos a "Add Entry", colocamos como nombre de la variable "ANDROID_SDK_ROOT", el tipo "Path" y el valor mencionado inicialmente, como se ve en la imagen.

     ![image](https://user-images.githubusercontent.com/31372472/48678794-eade8800-eb55-11e8-8b6e-aedd622482d3.png)
     
     Luego debemos configurar las variables ANDROID_SDK_TARGET y ANDROID_NATIVE_API_LEVEL, la primera tendrá el valor de "android-21" y la segunda el valor de "21", ahora estos valores dependen de la versión de android con la que van a trabajar, en mi caso yo estoy trabajando con el 5.0, por lo tanto me corresponde la 21, ahora si ustedes desean trabajar con otra pueden consultar en este link https://developer.android.com/ndk/guides/stable_apis?hl=es-419 y consultar en la tabla de niveles de api admitidos por la NDK. Ver las siguientes imágenes:
     
     ![image](https://user-images.githubusercontent.com/31372472/48678894-9805d000-eb57-11e8-883a-7983dea777f0.png)
     
     ![image](https://user-images.githubusercontent.com/31372472/48678935-02b70b80-eb58-11e8-8fa4-64fdf1ea4055.png)

     - g) Ahora damos click en "Configure".
     
     ![image](https://user-images.githubusercontent.com/31372472/48677770-c8457280-eb47-11e8-942d-2ca0abdaa5e5.png)
     
     Nos saldrá un error, similar al siguiente:
     
     ![image](https://user-images.githubusercontent.com/31372472/48677811-75b88600-eb48-11e8-8b89-dce195b61f84.png)
     
     Similar al siguiente:
     
         CMake Error at cmake/android/android_gradle_projects.cmake:1 (message):
  
         Android gradle-based build/projects are not supported in this version of OpenCV.

         You need to downgrade Android SDK Tools to version 25.2.5.

         Details: https://github.com/opencv/opencv/issues/8460

         Call Stack (most recent call first):
         cmake/android/OpenCVDetectAndroidSDK.cmake:204 (include)
         CMakeLists.txt:645 (include)

     Para solucionar ese error simplemente vamos a las variables del CMAKE, nos dirigimos a la variable BUILD_ANDROID_PROJECTS y le quitamos el check, como se ve en la imagen y después damos click en "Configurar" y finalmente compilara todo sin problemas, y en la última línea de los detalle saldrá "Configuring done", ver imagen.
     
     ![image](https://user-images.githubusercontent.com/31372472/48679122-3c891180-eb5a-11e8-9521-89a5f4b287bb.png)
     
     - g) Ahora como antepenúltima configuración, antes del gran paso de la configuración final debemos agregar 2 variables y quitar un check, las variables que debemos añadir son "ANDROID_PACKAGE" y "ANDROID_SET_OBSOLETE_VARIABLES", del tipo "Bool" y valor "True"; luego en la sección WITH quitamos el check a WITH_CUBLAS, como en la imagen siguiente:
     
     ![image](https://user-images.githubusercontent.com/31372472/48679865-3e0b0780-eb63-11e8-9e8e-b413d59c2eda.png)

     - h) Y ahora la configuración más esperada, indicamos la ruta del OpenCV_Contrib, los módulos externos, para ello vamos al grupo de "OPEN_CV" y colocamos la ruta de los módulos, en mi caso la ruta es "C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv_contrib-342-win\modules":
     
     ![image](https://user-images.githubusercontent.com/31372472/48680199-dce53300-eb66-11e8-9ddc-7e773e668e56.png)

     - i) A continuación apretamos "Configure" y luego de eso apretamos "Generate" y con eso se concluye la configuración.
     
     ![image](https://user-images.githubusercontent.com/31372472/48680283-c9869780-eb67-11e8-8de1-66c07c9c09f9.png)

- 8) Como uno de los últimos pasos levantamos un CMD y empezamos a realizar la construcción, primero, nos dirigimos dentro del CMD a la ruta , en mi caso, "C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv-342-win-sdk\build", dentro ejecutamos el siguiente comando:

     "C:\android-ndk-r16b\prebuilt\windows-x86_64\bin\make.exe -f Makefile"
     
     similar a la imagen y listo, comienza la magia.

     ![image](https://user-images.githubusercontent.com/31372472/48680366-bf18cd80-eb68-11e8-81a3-08ddba7a2142.png)
     
     ![image](https://user-images.githubusercontent.com/31372472/48680397-0e5efe00-eb69-11e8-9122-0825331e581c.png)
     
     ![image](https://user-images.githubusercontent.com/31372472/48682480-5cc6c980-eb76-11e8-9c3b-f17bc3eb6500.png)
     
     ![image](https://user-images.githubusercontent.com/31372472/48682508-8bdd3b00-eb76-11e8-8b7e-4db2a88f1807.png)
     
- 9) Finalizada la construcción entramos a la siguiente ruta, esta ruta es donde se crearon los archivos ".java":

     C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv-342-win-sdk\build\modules\java_bindings_generator\gen\java\org\opencv

     ![image](https://user-images.githubusercontent.com/31372472/48684543-1c6c4900-eb80-11e8-9a79-532b15fdacbb.png)
     
     y luego estas carpetas seleccionadas (las que contiene .java) las copiamos a la carpeta de OpenCV de Android (Ojo, Android), en mi caso la ruta destino es "C:\OpenCV-android-sdk\opencv-342-android-sdk\sdk\java\src\org\opencv", como se ve en la imagen.

     ![image](https://user-images.githubusercontent.com/31372472/48747313-ee027280-ec40-11e8-83a0-7681edc8949c.png)
     
- 10) Luego copiamos los archivos ".so" y ".a" de la carpeta "armeabi-v7a" en sus correspondienes dentro de OpenCV de Android, en mi caso la ruta origen es "C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv-342-win-sdk\build\lib\armeabi-v7a" y "C:\OpenCV-android-sdk\opencv-342-win-sdk\opencv-342-win-sdk\build\3rdparty\lib\armeabi-v7a" y las carpetas destino son en mi caso "C:\OpenCV-android-sdk\opencv-342-android-sdk\sdk\native\libs\armeabi-v7a", "C:\OpenCV-android-sdk\opencv-342-android-sdk\sdk\native\staticlibs\armeabi-v7a" y "C:\OpenCV-android-sdk\opencv-342-android-sdk\sdk\native\3rdparty\libs\armeabi-v7a" (se que la carpeta armeabi-v7a no es la única carpeta ABI de configuración, existen tambien arm64-v8a, armeabi, mips, mips64, x86 y x86_64, les explicare al final como anexo como obtenemos los archivos .a y .so para ellos).

     Copiar de esta carpeta origen:
     
     ![image](https://user-images.githubusercontent.com/31372472/48991144-a9268200-f0ff-11e8-974e-2c6a88a5f0f2.png)
     
     A este destino en OpenCV de Android, en este caso se copia el archivo ".so" a:
     
     ![image](https://user-images.githubusercontent.com/31372472/48991212-03bfde00-f100-11e8-8f70-21eb6c9a0051.png)
     
     Y las ".sa" en la siguiente carpeta de OpenCV de Android:
     
     ![image](https://user-images.githubusercontent.com/31372472/48991272-4386c580-f100-11e8-8dd0-5fcf9fd3da15.png)
     
     Luego, estos archivos ".sa":
     
     ![image](https://user-images.githubusercontent.com/31372472/48991338-8ba5e800-f100-11e8-9174-a02aad94a7a2.png)
     
     Al siguiente destino en OpenCV de Android:
     
     ![image](https://user-images.githubusercontent.com/31372472/48991847-e3455300-f102-11e8-9ae6-a47c5fd00c8f.png)
     
     Y listo, configuración completa, la puedes utilizar usando esta guía https://github.com/yucaret/OpenCV-AndroidStudio/blob/master/README.md.
     
Anexo:

   Para configurar las otras carpetas ABI solo se debe de reemplazar el punto 7 C por lo siguiente, dependiendo del tipo de configuración:
    
   ![image](https://user-images.githubusercontent.com/31372472/48992327-30c2bf80-f105-11e8-8c30-79a41e71db8c.png)
