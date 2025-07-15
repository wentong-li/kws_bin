# kws_bin

1. Project description

The project is to enable MFCC, followed by a CNN-based model to detect if a keyword from predefined list is present in the audio sample collect from PDM microphone.

MFCC implementation is based on CMSIS-DSP library, while it slightly differs to the built-in one. The modification is to ensure the setup matches the one in TensorFlow library used for training the model.

Button2 of LM20DK(PCA10184) is used to switch the inference backend. Press it and the backend with change to another. LED2 is used to indicate which backend is in use: LED ON for XXXX and OFF for tflite-micro.

2. Deploy the project

2.1 HW setup

A PDM microphone is required. Adafruit PDM MEMS Microphone Breakout (Product ID: 3492) is verified.

Connect the PDM microphone to the PDK as

DATA <--> P1.24

CLK <--> P1.23

CHANNEL SEL <--> GND

2.2 Test

Flash the binary to LM20DK. Monitor the outptut from serial port. Say a keyword and you should see the log message like

    Time used for inference: 6 ms.
    
    Time used for inference: 6 ms.
    
    Time used for inference: 7 ms.
    
    Time used for inference: 7 ms.
    
    Label: Yes in last 4 inferences.
