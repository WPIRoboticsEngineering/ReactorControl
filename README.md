# 2001BluetoothCode
Robotics 2001 Bluetooth code

This library contains code to communicate with a Bluetooth module on Serial3 for the final project of RBE2001. An example code, ReactorControl.ino is provided to give you a start for your final project code, and to show you how to use the library. By default, this code will only send a heartbeat message to the reactor control software using the packet structure outlined in the Bluetooth Communication Protocol document. This code may be used to test Bluetooth modules and RBE2001 shields, and if this is the first time you are using your Bluetooth module, it is recommended to test the software and hardware before making any modifications to the code.

In order to get started working on the final project, you should familiarize yourself with the resources provided in the Bluetooth section of the final project. For clarity, suggested order of reading is provided below.

1. To begin, read the Bluetooth Message Protocol in order to understand packets, their structure, and how your robot will be expected to communicate in order to accomplish the final project.

2. Clone the repo, using the instructions provided by the link in Bluetooth libraries.

3. To implement the code to react to ReactorControl messages, you must add variables and helper functions in order to respond to incoming messages in the Messages.cpp file under Messages::read, and make corresponding changes in the Messages.h file. For your convenience, kStopMovement is already completed. Notice the public boolean function Messages::isStopped(), and the corresponding method call in ReactorControl.ino, msg.isStopped(), which will return a boolean representing whether the robot should be stopped based on field control messages. The rest of the messages should have corresponding variables and public functions which may be called from your main program, similarly to ReactorControl.

Sending messages to the field controller, such as the Radiation Alert, requires further editing to BTComms and Messages in order to support your new message type and must calculate a correct checksum to ensure the message is not ignored by the field controller. The code for the reactor emulator may be helpful in implementing sending messages, as well as the heartbeat message in the example.

4. To understand the code in the repository, read the header files and the cpp files for ReactorControl, Messages, and BTComms. Remember that the ReactorControl example file has an instance of the Messages class msg, and the Message class has an instance of BTComms, comms. You should gain an understanding of the structure of the program, aided by the documentation, and how to proceed further.

5. To connect your robot to the field controller, read the How-to for Bluetooth for instructions on how to set up the hardware and connect to the field controller.
