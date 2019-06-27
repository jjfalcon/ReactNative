## Instalar herramientas react-native

Instalar brew (gestor de paquetes macOS)  
`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)”`

Instalar node (entorno de ejecución js para construir apps)  
`brew install node`

Instalar babel (conversion js EMACScript 2015 con versiones anteriores)  
`npm install --global babel-cli`

Instalar Webpack (gestor de paquete de modulos estaticos con dependencias)  
`npm install --save-dev webpack`

Instalar React Native (entorno desarrollo para apps)  
`npm install -g react-native-cli`

## Instalar xcode

Entrar en AppStore, buscar xcode app e instalar por defecto  
Comprobar instalacion correcta, creando un proyecto y ejecutando en simulador.

**ERRORES**  
  
**react-native run-ios xcrun error**  
xcrun: error: unable to find utility "instruments", not a developer tool or in PATH  
You need to launch XCode and agree to the terms first. Then go to Preferences > Locations and you'll see a select tag for Command Line Tools. Click this select box and choose the version of XCode you'll be using.  
After this you can go back to the command line and run react-native run-ios  

## Instalar Android Studio

Descargar de web ultima version, e instalar por defecto  
Comprobar instalación correcta, creando un proyecto y ejecutando en simulador.

Configurar Simulador -> Open Project -> Icono movil - configurar nuevo dispositivo  
- Dispositivo: Nexus 6
- OS: Pie 28 android 9
- Device Frame v

Lanzar dispositivo doble-click
Podemos cerrar Android Studio y emulador queda ejecutando

**ERRORES**  

**Si no esta instalado Java, JDK instalar**  
https://www.oracle.com/technetwork/java/javase/downloads/jdk12-downloads-5295953.html

**Si ocurre problema evaluating project ':app'**      
> SDK location not found. Define location with sdk.dir in the local.properties file or with an ANDROID_HOME environment variable.
Go to your React-native Project -> Android
Create a file local.properties
Open the file and paste your Android SDK path like below
in Windows sdk.dir = C:\\Users\\USERNAME\\AppData\\Local\\Android\\sdk
in macOS sdk.dir = /Users/USERNAME/Library/Android/sdk
in linux sdk.dir = /home/USERNAME/Android/Sdk
Replace USERNAME with your user name

Now, Run the react-native run-android in your terminal.

**Si no reconoce comando adb en terminal**  
`adb devices` devuelve los terminanles conectados

configurar PATH ejecutando desde terminal pero solo mantiene en sesion terminal  
`export PATH=~/Library/Android/sdk/platform-tools:$PATH`

configurar permanente en fichero: /etc/paths con permiso de sudo para editar e incluir al final  
`~/Library/Android/sdk/platform-tools`

Cerrar y abrir terminal para que los cambios tengan efecto.exit

## Instalar Visual Studio Code

Descargar desde web e instalar

[Para ejecutar desde terminal](https://code.visualstudio.com/docs/setup/mac)  
Open the Command Palette (⇧⌘P) and type 'shell command' to find the Shell Command: Install 'code' command in PATH command.
Restart the terminal for the new $PATH value to take effect. You'll be able to type 'code .' in any folder to start editing files in that folder.

## Crear app helloworld (demo)

```
react-native init helloworld           //crear proyecto por defecto  
cd helloworld                          //entrar en proyecto creado
react-native run-ios                   //ejecutar proyecto en emulador/dispositivo ios   
react-native run-android               //ejecutar proyecto en emulador/dispositivo android  
```

Al ejecutar proyecto con emulador/dispositivo se genera proyecto y levanta servidor ejecucion.   
Al ejecutar se levanta emulador en iOS, y hay tener emulador en Android previamente ejecutado.  
Desde emulador se puede refrescar cambios manualmente CMD+R o automaticamente CMD+D y configurar HotLive 

Para refrescar cambios desde app:  
* cambiar texto en pantalla(editor) y salvar
* desde emulador CMD+R refresca app con cambios
* si emulador configurado en hot live, al salvar fichero se refresca automaticamente

## Ejecutar app helloworld en dispositivo iOS, Android

