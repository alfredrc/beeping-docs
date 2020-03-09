# Aplicación de iPhone

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/tutorials/iphone-hello/) | [Español](https://docs-es.beeping.io/tutorials/iphone-hello/)

## Objetivo

El Objetivo de este tutorial es crear tu primera App de iPhone integrando la tecnología de **Beeping**.

Para ello seguiremos los siguientes pasos:

- Creación de un **beep**

- Creación de un proyecto de iPhone

- Instalación del SDK de iPhone

- Uso del SDK de iPhone

- Usar el simulador para capturar el conenido del **beep**

## Descargar la SDK

A continuación os dejamos los pasos que debes seguir para crear vuestra primera **App**.

Lo primero que debemos hacer es descargar el SDK de iPhone.

[Hacer click aquí para descargar el framework](https://github.com/beeping-io/sdk-iphone-objective-c/releases/download/1.0.0/Beeping.framework-objective-c.zip)

Una vez descargado lo descomprimimos y dejamos accesible el framework **beeping-framework** para más adelante.

## Creación del Beep

Para crear el **beep** sigue los pasos del anterior tutorial.

[Haz click aquí para acceder a la creación de tu primer **beep**](/tutorials/beeps/)

Una vez hayamos creado el **Beep** tendremos un fichero llamado **ultrasound.wav** con el contenido **qa020**. Dejamos accesible el fichero para reproducirlo más adelante.

## Creación de app

A continuación creamos nuestra aplicación del iPhone.

Vamos a llamar a nuestra aplicación **beeping-hello**.

[![1](/assets/images/shoots/tutorials/iphone/1.png)](/assets/images/shoots/tutorials/iphone/1.png)
[![2](/assets/images/shoots/tutorials/iphone/2.png)](/assets/images/shoots/tutorials/iphone/2.png)
[![3](/assets/images/shoots/tutorials/iphone/3.png)](/assets/images/shoots/tutorials/iphone/3.png)
[![4](/assets/images/shoots/tutorials/iphone/4.png)](/assets/images/shoots/tutorials/iphone/4.png)

## Instalación del framework

- Seleccionamos el target **beeping-hello** ( Figura 1 )

[![5](/assets/images/shoots/tutorials/iphone/5.png)](/assets/images/shoots/tutorials/iphone/5.png)

- Arrastramos el Framework de iPhone al siguiente directorio ( Figura 2 ):

[![6](/assets/images/shoots/tutorials/iphone/6.png)](/assets/images/shoots/tutorials/iphone/6.png)

- Asegurar que la instalación se ha hecho correctamente: 

Para ello debemos asegurarnos de que nuestro Framework está linkado correctamente.

* El Framework debe estar presente en la sección "Frameworks, Libraries, and Embedded Content"

[![7](/assets/images/shoots/tutorials/iphone/7.png)](/assets/images/shoots/tutorials/iphone/7.png)

!!! info "Opción Embed"

    It is very possible that by dragging the Framework the **Embed** option
    default to **Do not Embed**. If applicable
    we must change the option to **Embed & Sign**

[![8](/assets/images/shoots/tutorials/iphone/8.png)](/assets/images/shoots/tutorials/iphone/8.png)

* El Framework también debe estar presente en la sección **Build Phases** y revisar el apartado **Link Binary With Libraries**

!!! info "Opción Status"

    El parámetro **Status** debe tener como valor **Required**

[![9](/assets/images/shoots/tutorials/iphone/9.png)](/assets/images/shoots/tutorials/iphone/9.png)

Una vez se cumpla todo lo que hemos explicado con anterioridad, el **Framework de Beeping** estará bien instalado.

## Implemetar la SDK

El código que debemos escribir para implementar el protocolo de Beeping es muy simple.

A continuación os dejamos los pasos para implementar el código fuente en vuestra app.

- Abrir el fichero **ViewController.h**

- Incluir el header del Framework

``` C++ hl_lines="11"

//
//  ViewController.h
//  beeping-hello
//
//  Created by ---- on 07/03/2020.
//  Copyright © 2020 ----. All rights reserved.
//

#import <UIKit/UIKit.h>

#import <Beeping/Beeping.h>

@interface ViewController : UIViewController

@end

```

- Declarar el objeto Beeping

``` C++ hl_lines="15"

//
//  ViewController.h
//  beeping-hello
//
//  Created by ---- on 07/03/2020.
//  Copyright © 2020 ----. All rights reserved.
//

#import <UIKit/UIKit.h>

#import <Beeping/Beeping.h>

@interface ViewController : UIViewController

    @property (strong, nonatomic) Beeping *beepingManager;

@end

```

- Añadir el protocolo de Beeping

``` C++ hl_lines="13"

//
//  ViewController.h
//  beeping-hello
//
//  Created by ---- on 07/03/2020.
//  Copyright © 2020 ----. All rights reserved.
//

#import <UIKit/UIKit.h>

#import <Beeping/Beeping.h>

@interface ViewController : UIViewController <beepingDelegate>

    @property (strong, nonatomic) Beeping *beepingManager;

@end

```

- Abrir el fichero **ViewController.m**

- Crear la instancia de Beeping y asignar el protocolo de la SDK en el delegate

``` C++ hl_lines="21 22 23 24 25 26 27 28 29"

//
//  ViewController.m
//  beeping-hello
//
//  Created by ----- on 07/03/2020.
//  Copyright © 2020 -----. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view.
    
    if ( _beepingManager == NULL ) {
        
        // Instance Creation
        _beepingManager = [Beeping instance];
        
        // Self reference
        _beepingManager.delegate = self ;
        
    }
}

@end

```

- Abrir la consola para visualizar los logs

[![10](/assets/images/shoots/tutorials/iphone/10.png)](/assets/images/shoots/tutorials/iphone/10.png)

- Arrancar el simulador

En este punto la aplicación aparecerá en blanco, pero fijaros en las líneas de la consola.

``` bash

2020-03-07 14:13:28.180636+0100 beeping-hello[3865:16310305] BeepingCoreLib version 0.9.7 [31052017]
2020-03-07 14:13:28.180767+0100 beeping-hello[3865:16310305] Configuration NONAUDIBLE
2020-03-07 14:13:28.181241+0100 beeping-hello[3865:16310305] C++ DecoderNonAudibleMultiTone
2020-03-07 14:13:28.422437+0100 beeping-hello[3865:16310525] [plugin] AddInstanceForFactory: No factory registered for id <CFUUID 0x600002041680> F8BB1C28-BAE8-11D6-9C31-00039315CD46
2020-03-07 14:13:28.464858+0100 beeping-hello[3865:16310305] BeepingCore.framework version 1.0.4 [20012017]

```

Lo que os están diciendo estas líneas es que el objeto de Beeping se ha inicializado correctamente

- Implementar el protocolo.

``` C++ hl_lines="33 34 35 36 37 38 39"

//
//  ViewController.m
//  beeping-hello
//
//  Created by ----- on 07/03/2020.
//  Copyright © 2020 -----. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view.
    
    if ( _beepingManager == NULL ) {
        
        // Instance Creation
        _beepingManager = [Beeping instance];
        
        // Self reference
        _beepingManager.delegate = self ;
        
    }
    
}

// BEEPING DELEGATE IMPLEMENTATION

- (void) beepIdWith:(NSString *)beep_id {
    
    NSLog(@"The Beep data is: %@", beep_id );
    
}


@end

```

!!! info "Callback"

    Cuando la SDK detecte un **beep** esta función será
    llamada automáticamente, y recibirá como parámetro
    el contenido del **beep**. Cuando esto suceda en nuestra
    App, lo que hacemos es mostrar el contenido del **beep**
    en nuestra consola.

- Abrimos el fichero Info.plist

- Añadimos un campo **String**

- El parámetro que hay que añadir es: **Privacy - Microphone Usage Description**

- El valor que añadiremos será: **We need acces to your microphone to use Beeping**

!!! info "Microphone"

    Para poder escuchar el ultrasonido y decodificar su contenido, 
    la SDK necesita acceso al micrófono par apoder oir lo que le
    estamos enviando.

- Le decimos a Beeping que se ponga a escuchar

``` C++ hl_lines="31 32"

//
//  ViewController.m
//  beeping-hello
//
//  Created by ----- on 07/03/2020.
//  Copyright © 2020 -----. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view.
    
    if ( _beepingManager == NULL ) {
        
        // Instance Creation
        _beepingManager = [Beeping instance];
        
        // Self reference
        _beepingManager.delegate = self ;
        
    }
    
    // Listening ...
    [_beepingManager listen] ;
    
}

// BEEPING DELEGATE IMPLEMENTATION

- (void) beepIdWith:(NSString *)beep_id {
    
    NSLog(@"The Beep data is: %@", beep_id );
    
}


@end

```

- Le decimos a Beeping que deje de escuchar, una vez hemos leído el contenido del beep

``` C++ hl_lines="42 43 44 45 46 47"

//
//  ViewController.m
//  beeping-hello
//
//  Created by ----- on 07/03/2020.
//  Copyright © 2020 -----. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view.
    
    if ( _beepingManager == NULL ) {
        
        // Instance Creation
        _beepingManager = [Beeping instance];
        
        // Self reference
        _beepingManager.delegate = self ;
        
    }
    
    // Listening ...
    [_beepingManager listen] ;
    
}

// BEEPING DELEGATE IMPLEMENTATION

- (void) beepIdWith:(NSString *)beep_id {
    
    NSLog(@"The Beep data is: %@", beep_id );

    if ( _beepingManager != NULL ) {
        
        // Stop Listening ...
        [_beepingManager stop] ;
        
    }
    
}


@end

```

## La magia

Lo que vamos a hacer ahora es probar nuestra aplicación.

Para probar nuestra aplicación debemos tener a mano dos elementos:

- Nuestro fichero **ultrasound.wav** que es nuestro **beep** que contiene el valor **qa020**

- La aplicación que acbamos de crear

Lo primero que debemos hacer es ejecutar nuestra aplicación de iPhone.

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

