# Project_B
Containing files and also the B Project including a component recognition with an AI model built with Edge Impulse (same as the recognition project on the other repository)


First of all, we need to recognize thanks to the model implementend on the Arduino 33 BLE Lite some components scanned by a camera Arduino_OV767 and get that information into a nodered which will count each component. The Arduino wil lcommunciate with BLE with my computer in which I'm working on the nodered. 



Let's explain one of the major problem that I met. My model wouldn't compile because of some files missing and I didn't understand why at the beggining. I got that error : 

Fatal error: can't create C:\Users\Sofia\AppData\Local\Temp\arduino\sketches\ADD78443669BC46F8D9C5A8B82CE25B3\libraries\Electronic_components_recognition_CCN_training__inferencing\edge-impulse-sdk\porting\espressif\ESP-NN\src\convolution\esp_nn_conv_s8_filter_aligned_input_padded_esp32s3.S.o: No such file or directory
Assembler messages:
Fatal error: can't create C:\Users\Sofia\AppData\Local\Temp\arduino\sketches\ADD78443669BC46F8D9C5A8B82CE25B3\libraries\Electronic_components_recognition_CCN_training__inferencing\edge-impulse-sdk\porting\espressif\ESP-NN\src\convolution\esp_nn_depthwise_conv_s16_mult1_3x3_no_pad_esp32s3.S.o: No such file or directory

it seems that's something talking about esp32 and I'm not using that device. I solved that by re-working on the deployment-part in Edge Impulse. i think that with the optimization propose by Edge Impulse some files might be lost event if there are not used in my case. I also changed the estimated device in which implementing the model. Here's my Edge-impulse page : 



![Edge impulse image](https://github.com/SofianeBNA/Project_B/assets/148438130/7c1a5e56-7197-4ca8-955a-1c46a4bb117d)


Then, I implemented the connection BLE between my nodered and the Arduino and After I will work on the data transmission. 

For the Arduino part, I took a code generated for the BLE communication. I implemented that on my IA code. Here's some pictures of the implementation : 






Let's move on the nodered part. I began with a simple flow to test the BLE connection : 

![image](https://github.com/SofianeBNA/Project_B/assets/148438130/a549e0be-cb65-4471-9af5-8cec0410c50e)


I have connected now the Nodered with the Arduino. 


I suceeded to communicate between the Arduino and the Nodered but now I need to transmit the data correctly and count them into the nodered. 



