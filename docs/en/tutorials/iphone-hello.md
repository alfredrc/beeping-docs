# iPhone App

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.io/tutorials/iphone-hello/) | [Spanish](https://docs-es.beeping.io/tutorials/iphone-hello/)

## Objective

The objective of this tutorial is to create your first iPhone App integrating **Beeping** technology.

To do this we will follow the following steps:

- A **Beep** creation

- Creating an iPhone project

- Instalación del SDK de iPhone

- IPhone SDK installation

- Use the simulator to capture the content of the **beep**

## Download the SDK

Here are the steps you must follow to create your first **App**.
    
The first thing we should do is download the iPhone SDK.

[Click here to download the framework](https://github.com/beeping-io/sdk-iphone/releases/download/1.0.0/Beeping.framework.zip)

Once downloaded we unzip it and leave the **beeping-framework** file accessible for later.

## Beep Creation

To create the **beep** follow the steps in the previous tutorial.

[Click here to access the creation of your first **beep**](/tutorials/beeps/)

Once we have created the **Beep** we will have a file called **ultrasound.wav** with the content **qa020**. We leave the file accessible to play later.

## App creation

Next we create our iPhone application.

Let's call our **beeping-hello** application.

[![1](/assets/images/shoots/tutorials/iphone/1.png)](/assets/images/shoots/tutorials/iphone/1.png)
[![2](/assets/images/shoots/tutorials/iphone/2.png)](/assets/images/shoots/tutorials/iphone/2.png)
[![3](/assets/images/shoots/tutorials/iphone/3.png)](/assets/images/shoots/tutorials/iphone/3.png)
[![4](/assets/images/shoots/tutorials/iphone/4.png)](/assets/images/shoots/tutorials/iphone/4.png)

## Framework Installation

- We select the **beeping-hello** target (Figure 1)

[![5](/assets/images/shoots/tutorials/iphone/5.png)](/assets/images/shoots/tutorials/iphone/5.png)

- We drag the iPhone Framework to the following directory (Figure 2):

[![6](/assets/images/shoots/tutorials/iphone/6.png)](/assets/images/shoots/tutorials/iphone/6.png)

- Ensure that the installation has been done correctly:

To do this we must ensure that our Framework is correctly linked.

* The Framework must be present in the "Frameworks, Libraries, and Embedded Content" section

[![7](/assets/images/shoots/tutorials/iphone/7.png)](/assets/images/shoots/tutorials/iphone/7.png)

!!! info "Embed option"

    Es muy posible que al arrastrar el Framework la opción **Embed**
    tenga comom valor por defecto **Do not Embed**. Si fuera el caso 
    debemos cambiar la opción a **Embed & Sign**

[![8](/assets/images/shoots/tutorials/iphone/8.png)](/assets/images/shoots/tutorials/iphone/8.png)

* The Framework must also be present in the **Build Phases** section and review the **Link Binary With Libraries** section

!!! info "Status option"

    The **Status** parameter must have the **Required** value

[![9](/assets/images/shoots/tutorials/iphone/9.png)](/assets/images/shoots/tutorials/iphone/9.png)

Once everything we have explained before is fulfilled, the **Beeping Framework** will be well installed.

## Implement the SDK

The code we must write to implement the Beeping protocol is very simple.

Here are the steps to implement the source code in your app.

- Open the file **ViewController.h**

- Include the header of the Framework

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

- Declare the Beeping Object

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

- Add the Beeping protocol

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

- Open the file **ViewController.m**

- Create the Beeping instance and assign the SDK protocol in the delegate

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

- Open the console to view the logs

[![10](/assets/images/shoots/tutorials/iphone/10.png)](/assets/images/shoots/tutorials/iphone/10.png)

- Start the simulator

At this point the application will appear blank, but look at the console lines.

``` bash

2020-03-07 14:13:28.180636+0100 beeping-hello[3865:16310305] BeepingCoreLib version 0.9.7 [31052017]
2020-03-07 14:13:28.180767+0100 beeping-hello[3865:16310305] Configuration NONAUDIBLE
2020-03-07 14:13:28.181241+0100 beeping-hello[3865:16310305] C++ DecoderNonAudibleMultiTone
2020-03-07 14:13:28.422437+0100 beeping-hello[3865:16310525] [plugin] AddInstanceForFactory: No factory registered for id <CFUUID 0x600002041680> F8BB1C28-BAE8-11D6-9C31-00039315CD46
2020-03-07 14:13:28.464858+0100 beeping-hello[3865:16310305] BeepingCore.framework version 1.0.4 [20012017]

```

What these lines are telling you is that the Beeping object has been initialized correctly

- Implement the protocol.

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

    When the SDK detects a **beep** this function will be
    called automatically, and you will receive as a parameter
    The content of the **beep**. When this happens in our
    App, what we do is show the content of the **beep**
    in our console.

- We open the file Info.plist

- We add a **String** field

- The parameter to be added is: **Privacy - Microphone Usage Description**

- The value to be added is: **We need acces to your microphone to use Beeping**

!!! info "Microphone"

    In order to listen to the ultrasound and decode its content,
    the SDK needs access to the microphone to hear what
    we are sending.

- We tell Beeping to listen

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

- We tell Beeping to stop listening, once we have read the content of the beep

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

## The magic

What we are going to do now is test our application.

To test our application we must have two elements at hand:

- Our **ultrasound.wav** file that is our **beep** that contains the value **qa020**

- The application we just created

The first thing we should do is run our iPhone application.

If you look at our console we will see a new line that indicates that the application is in listening mode:

``` bash hl_lines="7"

2020-03-07 14:13:28.180636+0100 beeping-hello[3865:16310305] BeepingCoreLib version 0.9.7 [31052017]
2020-03-07 14:13:28.180767+0100 beeping-hello[3865:16310305] Configuration NONAUDIBLE
2020-03-07 14:13:28.181241+0100 beeping-hello[3865:16310305] C++ DecoderNonAudibleMultiTone
2020-03-07 14:13:28.422437+0100 beeping-hello[3865:16310525] [plugin] AddInstanceForFactory: No factory registered for id <CFUUID 0x600002041680> F8BB1C28-BAE8-11D6-9C31-00039315CD46
2020-03-07 14:13:28.464858+0100 beeping-hello[3865:16310305] BeepingCore.framework version 1.0.4 [20012017]

2020-03-07 14:43:01.821260+0100 beeping-hello[4001:16327281] [Beeping [info]] Listening ...

```

Now we play our **beep** and the magic becomes reality.

Check what has happened in our console:

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

If you look closely at the console, the first line informs us that **Beeping** has detected a ulltrasound, with information.

In the second line we are told that the format of the **beep** is
correct, and the following lines what they do is read the content and undo the information.

Once the process is finished, we are informed that the decryption has worked correctly
and internally what the SDK does is call the function that we have created and therefore receives the callback.

What it does is write this function in our console in the content of the **beep** that we have sent you. In our case the following
Information: **qa020**.

Once we have shown the information through the console, what we have done is stop listening to our app and that is what our log shows us in the last line.

## API

Below we show you the API of the **Beeping framework** for iPhone:

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

Here you have a series of links related to BeepBox:

- [Components: iPhone SDK](/components/sdk-iphone/)

- [Compile "Core System" to iPhone SDK](/components/core/)

## Quote

!!! quote "Ralph Waldo Emerson"
    A great man is always willing to be little.
