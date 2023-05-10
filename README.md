# Transformers-PCB-BADGE-Autobots

[![AQhBpQrfmg8](https://i.imgur.com/sDV7OV2.jpeg)](https://www.youtube.com/watch?v=vlJoQAzjYDo)


Wanted to generate a LED fading effect (fade-in and fade-out) for my upcoming video tutorial using the 555 timer IC.
I already have a video where I used LM358 Dual Operational Amplifier IC and another one with Arduino to generate the LED fading effect.

YouTube, is full of video showing how to generate the fading effect using 555 timer IC. However, none of them produce a true fading effect. 
Some just fades-in but never fades-out. And there is literally no explanation of how they are generating the fading effect other than just showing how to assemble the components.

In this tutorial, I am going to show you guys how to create a true LED fading effect using the 555 timer IC. I will also explain how the circuit works and how changing components change the fading effect of the LEDs.

Video: https://www.youtube.com/watch?v=vlJoQAzjYDo


Components Required
-------------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgOz0wyyaN03NbdhGI7GzxS1lkuE6uMGXtHuzYCdO2xwHryP4oiJ5npXO7jRuzihIEDn_Jf5vhWGHbgNaGM9u9EYzJ6SMmRkMHXtbk-Ai3aJhMGeEItiv103XMO9CNs_GkNYA3eLMusXYJ4cp9sq02SD-o_6pzS-nOIStvs7u2ALVUe60mAiYta89Uy/s1054/4.png)

For this tutorial you need:
1 x 555 Timer IC
1 x 47KΩ Resistor
1 x 220Ω Resistor
1 x BC548 NPN Transistor
1 x 33µF Capacitor, and
1 x Few Blue LEDs


Quick Recap
-----------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgarAvhBoyA0ffWZ7xMvWr5E4PdaF14nY8jvrp0e2-cACbwZuegLm9yHP3viTL83lOhd6PS334yNNGISELjnP9R4iBws2HOB7qcxQRLShbr8ZX74JdHL0Ta-d1-gqtL2F91jkFK4Fgk79UaR_3vj0Jt_MqRZNOU2bfAKnzSdU-lTCTdmezZHPTMVy2n/s1054/2.png)
In my last tutorial I created a "IC555 Led Fader Module" and explained how the circuit works. In this tutorial, I am going to use the same LED fader circuit to create a fading effect for the eyes of the badge. 
So before going ahead, lets do a quick recap and find out how the LED fader circuit works with the help of an animation.


Circuit Diagram
---------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgyt71vZS4YBRGiQwPmWXgHLlq7qz6k7kPAs3Jn1lk2ZWvuu6H5JRH81lJ5rOEWvFgUFzvtxi88xcrA_3GhhqY0_1Tn1CFCkcHFPh3WtNYWktmfIuVIfUr7Lo5TQ6eYGBZhXcTkLAinune2AT7ZCBvACS9OwuzTivBSD7Z7PMG4svzX2lGHiXiUjudo/s1054/3.png)

The heart of this circuit is the 555 timer IC.
Pin No.1 of the IC is connected to GND.
By connecting Pin 2 and 6 of the 555 timer IC, we put the IC in astable mode. In astable mode, the 555 timer IC acts as an oscillator (re-triggering itself) generating square waves [PWM Signals] from the output Pin no. 3.
3 other components connect to this junction. 
1st one is the 33µF capacitor. The positive pin of the capacitor connects to the junction and the negative pin is connected to the GND.
2nd one is the 47KΩ resistor. One of its legs connects to the junction and the other leg connects to the Output pin, Pin No.3 of the IC.
3rd one is the Base of the BC548 NPN transistor. The collector of the transistor along with Pin 8 and 4 of the IC connects to the +ve terminal. of the battery. The LED along with its current limiting resistor is connected to the Emitter of the transistor.
That's it as simple as that. 


How The Circuit Works
---------------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgKbI8AFSYGq5oKI-fXPbAbcopGf_jPLtsCjmR6JI2cNWMrnNkY65fjf0DrIxYECRwZjFy6ZIdn-w50myIoaffGR2RKiQGKq8tNKV7fRUghug7_N7fGYaZMKyBfrwW3vdvfpx6PL6Y8X8_Qih-pHvwTxHhbtMbwJosguEF-MKt7RMgYUjna-2sjZNYV/s1054/6.png)

* When Pin 2 of the IC detects voltage LESS than 1/3rd of the supply voltage, it turns ON the output on Pin 3.
* And, when Pin 6 detects voltage MORE than 2/3rds of the supply voltage, it turns OFF the output.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhGusssxoPIIkR8rgy67y0I4yoOvm_FlrS1108j_X2oH6qEqrIQxrt6N4hu90fm_BaORDNDKGb3QMyAdrEJwYmfkwpl1BYrnItHQujgFXWNm076xLw3KJkuiE_IRqN7B3uDD2xOFVwf03TizOAgZHjo1ml93bVO2HsJzUldpL7vrv3MKxbXUL8EUvoJ/s1054/7.png)

This is how the trigger pin (Pin2) and the threshold pin (Pin6) of the 555 timer IC sense voltages and controls the output at Pin 3.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiufJxn8HpUxkInlFzPCXAeihB128xlnTwUGOs9_1tXjxrP6v9Oq_gi2UV5jgSdvMoOFjHB50uixACjc9B5aam4wAZvyxNwYmqvBA9U6IdWbGujHkGz3EeK1mUQKq6Md6PDhWIPRlOPpFRrP20O92x2auQQLN126xrt2fk3WBNYcUTAYdR-iB6oWWsg/s1054/8.png)

* The Capacitor attached to the circuit will be in a discharged state immediately after firing up the circuit. 
* So, the voltage at Pin 2 will be 0v which is less than 1/3rds of the supply voltage, this will turn ON the output on Pin 3.
* Since Pin 3 is looped back to Pin 2, it will start charging the Capacitor via the 47KΩ resistor.
* At the same time the base current of the transistor also increases causing the LED to slowly "fade-in".
* Once the voltage across the capacitor crosses 2/3rds of the supply voltage, Pin 6 turns OFF the output.
* This causes the capacitor to slowly discharge causing the base current to fall and hence the LED starts "fading-out".

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgXmj_C1D0spOzfk0vFAIzWn2pl2Vnb4x3oUO9oRc-HqLGvLc8e9Ge0_bnpJYP40ghMJUdheSl-3zbcp92-jFYSj_0KzJYUduf8DjmPJV_EAolqoipOtGayVkCXuqr11H28HRp058o0WKJI_GuseZOMU6m2t_N5PVBMSpMRCbUxYp1FmoMypuWbRT72/s1054/9.png)

* Once the voltage across the capacitor falls below 1/3rd of the supply voltage, Pin 2 turns ON the output, and the above cycle continues.
You can hook up a multimeter to the circuit to measure the charging and discharging of the capacitor.


Designing The PCB
-----------------
**Sorting Out Images**

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhSfwuYSHK9JfD8vT_xp2gh5N1M8ydelggP6nLg8RXkopVl1G80h9E2W7p0KFL7vqUnUvopf4X4OJDhd7ndXatYTk2V1sRA7Mxgv6sErZro-TIQFOJg-SBFb4J9OOjjaqNA9AatbO5f0ZyS3CRudHp1n3v_mY7rbrY60XB_d9nKPl8RAM8Ap1-3O2qw/s1054/6.png)

To start the designing process, I need a transparent PNG image of the "Transformers Logo".
So I went online, and did an "image search" and downloaded a black-and-white images of the Transformers Logo.

Now, using the "Paint.Net" application I opened up the PNG file. 
The image onscreen will be used for:
1. Creating the border outline of the badge
2. and also for creating the face on top of the top silk layer

To generate the "Border Outline" I need a DXF file. 
Looking at the image, we can see that the image is split into multiple parts. If I load this to generate a DXF file it will generate multiple pieces of the PCB. And obviously that's not what I am after. So, I joined all the small pieces into a single image.

**Generating DXF File**

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhKMkjQ_6Azb4Pi996iZznAC5gdwPBOiJ4dvGH8jtdeR6rJ9rVpx5m1Wm24dSqHOOtFGv2hE5E8PtE8mnv2wpcaIwpui3rURJOfG-Fqw0eEQQrvO5I18BfyU9vIvDRVKl0C4eCL0ZAhzOlek-J1lqI_37xGCVbn_g_95Ilc0mVTFu5UIUA1TRK_jema/s1054/9.png)

Then, I uploaded the images to "https://convertio.co/" to generate the DXF files. This website allows 10 free conversions in a day unless you have a paid account with them.  

**Creating the Badge**

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiUPoqKjsqKDi5NkJHQaEFdG_MM9OVzUHp_8LS4LNbtqdudQn_CFFZQ1Pc8-SW44r7_jTVHwEXwo4NfnJnIT9YR92Waaz_WC4u7k2TkL2rNWpc1_Yz7sG0-1cldnDRy4GANKIdhTv0zSQCSTEWoSGgqjXg5DKE7OMm88rybDHkDciFVsNEHwAKBlhTp/s1054/7.png)

Now, lets go ahead and add a "New PCB" to our project and remove the default board outlines.
Then import the DXF files via File > Import > DXF menu. Make sure you have the "BoardOutLine" selected under layers when you import the DXF file.

Now, lets import the image that will go on the Top Silk Layer. Select the "TopSilkLayer" and then import the image and move it inside the board outlines. Before going ahead, lets have a look at how the board looks like in 3D. As we can see the eyes and all other holes still have the blue PCB bits inside. So, let go ahead and remove them from our design.

To do so, select the "MultiLayer" from the "Layers and Objects" panel. Then select "Solid Region" from the "PCB Tools" panel and start drawing the region you want to exclude from your PCB. That's it as easy as that. Checking the PCB in 3D, we can see that the top bit has now a see-through hole in it. I repeated this step, for all other bits that I wanted to excluded from my PCB design.

Once the PCB design was sorted, I added all the electronic components to the board. Since I don't want any hole on my PCB, my choice was to either add SMD components on the board or to design the board in a way that I can solder THT components on it. I chose the second option and added all the THT components "however" without their holes. Instead of the holes I added some rectangles and circles from the "PCB Tools" panel on the "BottomLayer" and then exposed the copper. To finalize the design, I connected all the exposed pads as per the circuit diagram. That's it, all done. So, this is how the final design looks like.


The Board
---------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjIEQvIQWzdbT88B2SpNAAYg9YKHOLaLORjgZ3el471GDq53WgARTvCKK4nxpR2kcy3-_kJZh6P2MCGydHihyQTvst7Piq7IBg0RVLRdes4YGyyAjoR14sz0dZ40mlXz0FjOQ8PU7DXK80olvdXnXak36MD4Q9Zfdy7rvWbuiY5mFEQdlWMebWOnDpC/s1054/11.png)

So this is what came in the mailbag. Have a look at the quality, its absolutely mind-blowing.
At the back of the board are all the exposed copper parts for soldering the electronic components. 

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgl6G1S5TaZ2fv81WoWUI93nBJfClJlbjCI_6rkfQW8hZq7tee4gieGrRMoS_N0ytMOhEF7bIKxNzJlpki8IkawqxaQupQ0fps4IAYdNO2FGMDmZcCuXDDF4UvBXbXc9_JpdPPNd1XM-fZOXf-DvRsPkk_2AMKXSHD8HIIFzv4K_ZTKd2nKjbCrTHpb/s1054/10.png)

As mentioned earlier, I could have designed the board with SMD components, however I wanted to design something that someone with "0" SMD soldering knowledge can also do.


Soldering
---------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhCYLb5-dUW1ekGdm_WQh3H2aV0spN9FlC6Bf7Sky_1Puu4zGJYHHu0OxbQQ6YI--TcquQxhkwUF6NCBTR1EmftBaJeGxsgLALajMSvObl7eVP5sqlXejRKQ_5-LADIkTqFgcqe1zNYidN62tkxynG-9KAeXpGTq_xsd7Gn4165zoGZlqwSTTteSwjb/s1054/12.png)

Alright, now lets go ahead and solder the components to the board.

Lets first soldered the 555 Timer IC to the board, then lets soldered the two resistors to the board. Next, lets soldered the 33µF Capacitor followed by the NPN transistor to the board.
To conclude the setup lets soldered the 2 x LEDs to the board. You can power this circuit by providing voltage between 5V to 15Vs.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhZ-XocddbKeMi6TjYN3pNFDgqBdOqLtBE-FmgxwqzJcbwNKp__6dP_zWIQdFtprqa4-39ukWTwDlUBgyODX1J0QiYpBFC16im96MH1AC6K8IeWQHYi2vFpGTi1vc-qv2DbhpDTdgUZRwqssHFDtDIwc7jw6XtI4coLfUw_atnYRO-whZecFyQY43L_/s1054/13.png)


Demo
----
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhHGMNGl5mV1khPiWWfQ4F3gDMLsgbBbC768EWTH4yizEemw5dglJwymoKjM53QYmFcump4IQ43cb21vw2dg86xbOQo7On4MlXkdZ2g1fwwYxT7Myg9QZLyDJ2BrDpHh42q44ACwds8rFFJchZjuG6wS4Eb54JlQz8GTCquWi3JJrFamFmJPXHRGapz/s1054/14.png)

So, this is how the final setup looks like. You can insert the bottom bit of the badge to a wooden-plank and put this on your desk to give your desk a flashy look.


Thanks
------
[![AQhBpQrfmg8](https://i.imgur.com/sDV7OV2.jpeg)](https://www.youtube.com/watch?v=vlJoQAzjYDo)

Thanks again for checking my post. I hope it helps you.
If you want to support me subscribe to my YouTube Channel: https://www.youtube.com/user/tarantula3

Video: https://youtu.be/vlJoQAzjYDo

Full Blog Post: https://diyfactory007.blogspot.com/2023/04/555LedFader.html


LED Fader Using 555 Timer IC: https://youtu.be/30wGujPnupw

LED Fader - With or Without Arduino: https://youtu.be/IIUsdICycOw

Adjustable Single/Dual LED Flasher Using 555 Timer IC: https://youtu.be/B1URFJywtcI



**Other Links:**

Gerber: https://www.pcbway.com/project/shareproject/Transformers_PCB_BADGE_15b0c565.html

Github: https://github.com/tarantula3/Transformers-PCB-BADGE-Autobots

Simulation: https://tinyurl.com/2qv266bg

What Is Forward Voltage: https://42electronics.com/blogs/learn-more/what-is-forward-voltage



**Support My Work:**

BTC:   1Hrr83W2zu2hmDcmYqZMhgPQ71oLj5b7v5

LTC:   LPh69qxUqaHKYuFPJVJsNQjpBHWK7hZ9TZ

DOGE:  DEU2Wz3TK95119HMNZv2kpU7PkWbGNs9K3

ETH:   0xD64fb51C74E0206cB6702aB922C765c68B97dCD4

BAT:   0x9D9E77cA360b53cD89cc01dC37A5314C0113FFc3

LBC:   bZ8ANEJFsd2MNFfpoxBhtFNPboh7PmD7M2

COS:   bnb136ns6lfw4zs5hg4n85vdthaad7hq5m4gtkgf23 Memo: 572187879

BNB:   0xD64fb51C74E0206cB6702aB922C765c68B97dCD4

MATIC: 0xD64fb51C74E0206cB6702aB922C765c68B97dCD4


Thanks, ca again in my next tutorial.

