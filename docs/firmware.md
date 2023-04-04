# Modifying the firmware

**Important:** Make sure you are using the newest version of the ESP32Servo library, or it will not work!

You need to open some files of the prototype 5 firmware and edit them as described here:

## _main.ino

**Remove** the following line:

```cpp
  pinMode(32, INPUT_PULLUP);
```

## input.ino

**Remove** these lines:

```cpp
  pinMode(PIN_MENU_BTN, INPUT_PULLUP);
  
  #if !TRIGGER_GESTURE
  pinMode(PIN_TRIG_BTN, INPUT_PULLUP);
  #endif
```


**Replace** this line:

```cpp
   return analogRead(UNMUX(pin));
```

with this line:

```cpp
   return analogRead(pin);
```

## lucidgloves-firmware.ino

Adjust the settings ot look like this. These lines are not all next to each other in the file, 
just find the corresponding lines and adjust the values.

**Important:** These are the settings for your right hand. If you are wiring up a left hand, you need to swap the values
pinky and thumb, and for index and ring.

Eagle-eyed viewers might notice that there is a WS2812 RGB LED on the board. The firmware defines a DEBUG_LED pin, but
doesn't use it. We are attaching the RGB LED to this pin. Of course, if the firmware eventually started using the
DEBUG_LED, it wouldn't work correctly with the WS2812 LED. If you feel like it, go ahead and implement both :)

```cpp
#define USING_SPLAY true
#define USING_MULTIPLEXER false

#define INVERT_A false
#define INVERT_B false
#define INVERT_JOY false
#define INVERT_MENU true
#define INVERT_CALIB false
#define INVERT_TRIGGER true
#define INVERT_GRAB false
#define INVERT_PINCH false

#define USING_FORCE_FEEDBACK true

#define PINS_MUX_SELECT   -1,  /*S0 pin*/ \
                          -1,  /*S1 pin*/ \
                          -1,  /*S2 pin*/ \
                          -1   /*S3 pin*/
#define MUX_INPUT -1

#define PIN_MENU_BTN  45
#define PIN_A_BTN     21
#define PIN_B_BTN      3
#define PIN_TRIG_BTN  46
#define PIN_GRAB_BTN  48
#define PIN_PNCH_BTN  47
#define PIN_CALIB     36

#define PIN_JOY_X     13
#define PIN_JOY_Y     14
#define PIN_JOY_BTN   35

#define DEBUG_LED     23  

#define PIN_PINKY      6
#define PIN_RING      10
#define PIN_MIDDLE    18
#define PIN_INDEX     15
#define PIN_THUMB      2

#define PIN_PINKY_SECOND    5
#define PIN_RING_SECOND    11
#define PIN_MIDDLE_SECOND   8
#define PIN_INDEX_SECOND   16
#define PIN_THUMB_SECOND    1

#define PIN_PINKY_SPLAY     4
#define PIN_RING_SPLAY     12
#define PIN_MIDDLE_SPLAY    9
#define PIN_INDEX_SPLAY    17
#define PIN_THUMB_SPLAY     7

#define PIN_PINKY_MOTOR    42
#define PIN_RING_MOTOR     41
#define PIN_MIDDLE_MOTOR   40
#define PIN_INDEX_MOTOR    39
#define PIN_THUMB_MOTOR    38
```
