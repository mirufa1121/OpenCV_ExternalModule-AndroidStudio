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

- 1) Configurar Variables de Entorno, después de instalar todo lo que se menciono líneas arriba, se debe de configurar algunas variables de entorno. En mi caso no tenia configurado el ANT_HOME y el JAVA_HOME

     ![image](https://user-images.githubusercontent.com/31372472/48667204-3aae4800-ea9f-11e8-9ab7-b9019156f0af.png)
     
     Tambien debes de configurar en el "path", el MINGW, Java Tools, SDK Tools, SDK Platform Tools, Java y Ant.
     ![image](https://user-images.githubusercontent.com/31372472/48667235-c6c06f80-ea9f-11e8-99b8-9f4052c90aa3.png)

- 2) Configurar el JDK, para ello debes de primero abrir tu Android Studio, luego ingresar a File --> Project Structure, luego dar click  en "SDK Location" y en la sección de "JDK Location", quitar el check y colocar a ruta del JDK, en mi caso la ruta de mi sdk es:
     
     C:\Program Files\Java\jdk1.8.0_181
     
     La configuración debe de quedar como la siguiente imagen y darle "OK".
     
     ![image](https://user-images.githubusercontent.com/31372472/48667142-d6d74f80-ea9d-11e8-99e8-46874ce50331.png)
