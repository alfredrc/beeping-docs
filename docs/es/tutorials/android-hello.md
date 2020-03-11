# Aplicación de Android

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/tutorials/android-hello/) | [Español](https://docs-es.beeping.io/tutorials/android-hello/)

## Objetivo

El Objetivo de este tutorial es crear tu primera App de Android integrando la tecnología de **Beeping**.

Para ello seguiremos los siguientes pasos:

- Creación de un **beep**

- Creación de un proyecto de Android

- Instalación del SDK de Android

- Uso del SDK de Android

- Usar el dispositivo para capturar el conenido del **beep**

## Descargar la SDK

A continuación os dejamos los pasos que debes seguir para crear vuestra primera **App**.

Lo primero que debemos hacer es descargar el SDK de Android.

[Hacer click aquí para descargar el framework](https://github.com/beeping-io/sdk-android/releases/download/1.0.0/AndroidBeepingCore-release.aar.zip)

Una vez descargado lo descomprimimos y dejamos accesible el framework **AndroidBeepingCore-release.aar** para más adelante.

## Creación del Beep

Para crear el **beep** sigue los pasos del anterior tutorial.

[Haz click aquí para acceder a la creación de tu primer **beep**](/tutorials/beeps/)

Una vez hayamos creado el **Beep** tendremos un fichero llamado **ultrasound.wav** con el contenido **qa020**. Dejamos accesible el fichero para reproducirlo más adelante.

## Creación de app

A continuación creamos nuestra aplicación de Android.

Nosotros vamos a utilizar Android Studio.

Vamos a llamar a nuestra aplicación **beeping-hello**.

[![1](/assets/images/shoots/tutorials/android/1.png)](/assets/images/shoots/tutorials/android/1.png)
[![2](/assets/images/shoots/tutorials/android/2.png)](/assets/images/shoots/tutorials/android/2.png)
[![3](/assets/images/shoots/tutorials/android/3.png)](/assets/images/shoots/tutorials/android/3.png)
[![4](/assets/images/shoots/tutorials/android/4.png)](/assets/images/shoots/tutorials/android/4.png)

## Instalación del framework

- Copiamos el framework dentro del siguiente directorio de nuestra app:

``` bash
$ cp AndroidBeepingCore-release.aar [APP]/app/libs/AndroidBeepingCore.aar
```

!!! warning "AndroidBeepingCore"

    Al ejecutar el comando de copia lo que hemos hecho
    es cambiarle el nombre al framework. Dentro de nuestra
    App el framework debe llamarse **AndroidBeepingCore.arr**

- Importamos el framework a nuestro proyecto:

[![5](/assets/images/shoots/tutorials/android/5.png)](/assets/images/shoots/tutorials/android/5.png)
[![6](/assets/images/shoots/tutorials/android/6.png)](/assets/images/shoots/tutorials/android/6.png)
[![7](/assets/images/shoots/tutorials/android/7.png)](/assets/images/shoots/tutorials/android/7.png)

- Abrir el fichero build.gradle (Module: app)

[![8](/assets/images/shoots/tutorials/android/8.png)](/assets/images/shoots/tutorials/android/8.png)

- Modificar el minSdkVersion a la versión 26: 

``` java hl_lines="3"

defaultConfig {
        applicationId "io.beeping.beeping_hello"
        minSdkVersion 26
        targetSdkVersion 28
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }
```

- Conecta un dispositivo Android por USB

- Selecciona el dispositivo en Android Studio y ejecuta la aplicación.

Si la apliación se abre correctamente, el **Framework de Beeping** estará bien instalado.

## Implemetar la SDK

El código que debemos escribir para implementar el protocolo de Beeping es muy simple.

A continuación os dejamos los pasos para implementar el código fuente en vuestra app.

- Abrimos el fichero AndroidManifest.xml y añadimos las siguientes líneas:

``` xml hl_lines="5 6"

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="io.beeping.beeping_hello">

    <uses-permission android:name="android.permission.RECORD_AUDIO"></uses-permission>
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"></uses-permission>

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

```

- Abrimos el fichero MainActivity.java y añadimos los headers:

``` java hl_lines="7 8 9"

package io.beeping.beeping_hello;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import com.beeping.AndroidBeepingCore.BeepingCore;
import com.beeping.AndroidBeepingCore.BeepingCoreEvent;
import com.beeping.AndroidBeepingCore.BeepingCoreJNI;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}

```

- Añadimos la implementación de Beeping

``` java hl_lines="12 20 21 22 23"

package io.beeping.beeping_hello;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import com.beeping.AndroidBeepingCore.BeepingCore;
import com.beeping.AndroidBeepingCore.BeepingCoreEvent;
import com.beeping.AndroidBeepingCore.BeepingCoreJNI;

public class MainActivity extends AppCompatActivity
        implements BeepingCoreEvent {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    public void beepIdWith(String beepId) {
        System.out.println("The BeepId is:" + beepId);
    }
}


```

!!! info "Callback"

    Cuando la SDK detecte un **beep** la función **beepIdWith** será
    llamada automáticamente, y recibirá como parámetro
    el contenido del **beep**. Cuando esto suceda en nuestra
    App, lo que hacemos es mostrar el contenido del **beep**
    en nuestra consola.

- Declaración del objeto Beeping

``` java hl_lines="14"

package io.beeping.beeping_hello;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import com.beeping.AndroidBeepingCore.BeepingCore;
import com.beeping.AndroidBeepingCore.BeepingCoreEvent;
import com.beeping.AndroidBeepingCore.BeepingCoreJNI;

public class MainActivity extends AppCompatActivity
        implements BeepingCoreEvent {

    BeepingCore beeping;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    public void beepIdWith(String beepId) {
        System.out.println("The BeepId is:" + beepId);
    }
}

```

- Se inicializa el objeto de Beeping y le decimos que se ponga a escuchar

``` java hl_lines="20 21 23 24"

package io.beeping.beeping_hello;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import com.beeping.AndroidBeepingCore.BeepingCore;
import com.beeping.AndroidBeepingCore.BeepingCoreEvent;
import com.beeping.AndroidBeepingCore.BeepingCoreJNI;

public class MainActivity extends AppCompatActivity
        implements BeepingCoreEvent {

    BeepingCore beeping;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        // Init Beeping Framework
        beeping = new BeepingCore(this);

        // Listening
        beeping.startBeepingListen();

        setContentView(R.layout.activity_main);
    }

    @Override
    public void beepIdWith(String beepId) {
        System.out.println("The BeepId is:" + beepId);
    }
}

```

!!! info "Microphone"

    Para poder escuchar el ultrasonido y decodificar su contenido, 
    la SDK necesita acceso al micrófono par apoder oir lo que le
    estamos enviando.

- Le decimos a Beeping que deje de escuchar, una vez hemos leído el contenido del beep

``` java hl_lines="34 35"

package io.beeping.beeping_hello;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import com.beeping.AndroidBeepingCore.BeepingCore;
import com.beeping.AndroidBeepingCore.BeepingCoreEvent;
import com.beeping.AndroidBeepingCore.BeepingCoreJNI;

public class MainActivity extends AppCompatActivity
        implements BeepingCoreEvent {

    BeepingCore beeping;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        // Init Beeping Framework
        beeping = new BeepingCore(this);

        // Listening
        beeping.startBeepingListen();

        setContentView(R.layout.activity_main);
    }

    @Override
    public void beepIdWith(String beepId) {

        System.out.println("The BeepId is:" + beepId);

        // Stop listening
        beeping.stopBeepingListen();

    }
}


```

## La magia

Lo que vamos a hacer ahora es probar nuestra aplicación.

Para probar nuestra aplicación debemos tener a mano dos elementos:

- Nuestro fichero **ultrasound.wav** que es nuestro **beep** que contiene el valor **qa020**

- La aplicación que acbamos de crear

Lo primero que debemos hacer es ejecutar nuestra aplicación de Android.

************************************************


Si nos fijamos en nuestra consola veremos una nueva línea que nos indica que la aplicación está en modo de escucha:

``` bash hl_lines="7"

2020-03-07 14:13:28.180636+0100 beeping-hello[3865:16310305] BeepingCoreLib version 0.9.7 [31052017]
2020-03-07 14:13:28.180767+0100 beeping-hello[3865:16310305] Configuration NONAUDIBLE
2020-03-07 14:13:28.181241+0100 beeping-hello[3865:16310305] C++ DecoderNonAudibleMultiTone
2020-03-07 14:13:28.422437+0100 beeping-hello[3865:16310525] [plugin] AddInstanceForFactory: No factory registered for id <CFUUID 0x600002041680> F8BB1C28-BAE8-11D6-9C31-00039315CD46
2020-03-07 14:13:28.464858+0100 beeping-hello[3865:16310305] BeepingCore.framework version 1.0.4 [20012017]

2020-03-07 14:43:01.821260+0100 beeping-hello[4001:16327281] [Beeping [info]] Listening ...

```

Ahora ejecutamos nuestro **beep** y la magia se convierte en realidad.

Fijaros lo que ha pasado en nuestra consola:

``` bash hl_lines="1 2 21 23 24"

2020-03-07 14:44:15.199810+0100 beeping-hello[4023:16328812] BEGIN TOKEN FOUND!
2020-03-07 14:44:15.199971+0100 beeping-hello[4023:16328812] [Beeping [info]] BEEP_TOKEN_END_OK
2020-03-07 14:44:15.304691+0100 beeping-hello[4023:16328812] Token found! 26
2020-03-07 14:44:15.408884+0100 beeping-hello[4023:16328812] Token found! 10
2020-03-07 14:44:15.513293+0100 beeping-hello[4023:16328812] Token found! 0
2020-03-07 14:44:15.618080+0100 beeping-hello[4023:16328812] Token found! 2
2020-03-07 14:44:15.722645+0100 beeping-hello[4023:16328812] Token found! 0
2020-03-07 14:44:15.826769+0100 beeping-hello[4023:16328812] Token found! 0
2020-03-07 14:44:15.931384+0100 beeping-hello[4023:16328812] Token found! 0
2020-03-07 14:44:16.036250+0100 beeping-hello[4023:16328812] Token found! 0
2020-03-07 14:44:16.140386+0100 beeping-hello[4023:16328812] Token found! 5
2020-03-07 14:44:16.244719+0100 beeping-hello[4023:16328812] Token found! 11
2020-03-07 14:44:16.349270+0100 beeping-hello[4023:16328812] Token found! 25
2020-03-07 14:44:16.454256+0100 beeping-hello[4023:16328812] Token found! 29
2020-03-07 14:44:16.558209+0100 beeping-hello[4023:16328812] Token found! 5
2020-03-07 14:44:16.662571+0100 beeping-hello[4023:16328812] Token found! 0
2020-03-07 14:44:16.767269+0100 beeping-hello[4023:16328812] Token found! 20
2020-03-07 14:44:16.871958+0100 beeping-hello[4023:16328812] Token found! 26
2020-03-07 14:44:16.976103+0100 beeping-hello[4023:16328812] Token found! 16
2020-03-07 14:44:17.080627+0100 beeping-hello[4023:16328812] Token found! 19
2020-03-07 14:44:17.092184+0100 beeping-hello[4023:16328812] END DECODING OK! qa0200005
2020-03-07 14:44:17.092360+0100 beeping-hello[4023:16328812] [Beeping [info]] BEEP_TOKEN_END_OK
2020-03-07 14:44:17.092474+0100 beeping-hello[4023:16328812] The Beep data is: qa020
2020-03-07 14:44:17.092549+0100 beeping-hello[4023:16328812] [Beeping [info]] Stopped

```

Si os fijáis bien en la consola, la primera línea nos informa de que **Beeping** ha detectado un ulltrasonido, con información. 

En la segunda línea se nos indica que el formato del **beep** es 
correcto, y las líneas siguientes lo que hacen es leer el contenido y desenciptan la información. 

Una vez finalizo el proceso, se nos informa que la desencriptación ha funcionado correctamente
e internamente lo que hace ls SDK es llamar a la función que hemos creado y que por lo tanto recibe el callback.

Esta función lo que hace es escribir en nuestra consola en contenido del **beep** que le hemos enviado. En nuestro caso la siguiente
información: **qa020**.

Una vez hemos mostrado la información por la consola lo que hemos hecho es parar la escucha de nuestra app y eso es lo que nos muestra nuestro log en la última línea.

## API

A continuación os mostramos el API del **framework de Beeping** para iPhone:

### Object

| Name       | Object    | Type   |
| :--------- | :------:  | :------: |
| **Beeping**    | Beeping * | Pointer  |

### Methods

| Object       | Method    | Return | Description |
| :--------- | :------:  | :------: | :------: |
| **Beeping**    | [Beeping instance] | instance  | Object creation  |
| **Beeping**    | listen() | void  | Ready to listen beeps |
| **Beeping**    | stop() | void  | Stop listening beeps |

### Protocol

| Object       | Type  | Callback | Return |
| :---------: | :------:  | :------: | :------: |
| **Beeping**    | beepingDelegate | beepIdWith:(NSString *)beep_id  | void  |

## Links

Aquí te dejamos una serie de links relacionados con la SDK de iPhone:

- [Components: iPhone SDK](/components/sdk-iphone/)

- [Compilar "Core System" para el iPhone SDK](/components/core/)

## Frase

!!! quote "Ralph Waldo Emerson"
    Un gran hombre siempre está dispuesto a ser pequeño.

