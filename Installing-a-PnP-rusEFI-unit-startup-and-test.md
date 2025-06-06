# Installing a Plug-and-Play gerEFI Unit - Startup and Test

This guide is written for the firmware released August 6th 2020. The further away from this date your FW is, the less agreement you will have in specific locations of items in TunerStudio and terms used etc. HOWEVER, the basic principles should still apply.

1. [Download the gerEFI Bundle](Download) to get your gerefiXXX.ini file and serial port drivers.

2. Install [TunerStudio](http://www.tunerstudio.com/index.php/downloads) and [MegaLog Viewer](https://www.efianalytics.com/MegaLogViewer/download/) (the payed versions are highly recommended).

3. Create a new project in TunerStudio.
   *This is not a TunerStudio manual.
   *Most PnP gerEFI units can be powered through the USB port. So you can set it up in the comfort of your living room and have it communicate with Tunerstudio before it is installed in the car. It is highly recommended to try this approach.

4. Connect TunerStudio to your ECU. You will need a USB cable to establish communication between your tuning laptop and the gerEFI unit. There will typically be only one micro-USB port on a PnP unit.

   *Your laptop should give you an audible notification when you plug in the ECU with the ignition turned on. That means that it "sees" a new device connected to a USB port.

5. Under "Communications" -> "Communication Settings" [IMAGE] you should select the correct COM port for your gerEFI. You will usually see only two COM ports. Chances are, the one with the higher number is the gerEFI COM-port. For most cases, the selected Baud rate does not matter. If you can't establish communication, try baud rate 38,400 | 57,600 or 115,200. If that doesn't work, you may need to try a different COM port.

6. After selecting the COM-port (and baud rate), click on "Test Port". This should result in a "successful!" message. If you get a failed message, you need to adjust your settings. After a successful test of the port click "Accept".

7. With this your TunerStudio screen should come to life! You should see sensor inputs and some output values like ignition timing and dwell. Of course the values displayed miught not make a lot of sense, since your ECU is lacking a car, but at least you can see that TunerStudio and your computer are communicating.

## Getting your car running

### Step 1: (Optional)

Run your car on your stock ECU to warm it up. This may make it easier to start, especially when it's cold outside

### Step 2

Unplug your stock ECU and plug in your gerEFI PnP. You probably don't want to close the lid just yet, so you can observe blinky lights etc.

### Step 3

Turn on the ignition. DO NOT START THE CAR

### Step 4

Connect TunerStudio to your ECU.
With this your TunerStudio screen should come to life! You should see sensor inputs and some output values like ignition timing and dwell. If things are set up properly, you should see reasonable values for [Coolant temperature], [Air Intake temperature], [Battery Voltage], [Manifold Air Pressure] (should be near 100kpa if you're using a MAP snesor) and even your [throttle pedal position]. The values may show some jitters. Your rpms should be 0. Push your throttle pedal and see if you get a response. Congratulations- your gerEFI can "see" your car.

### Step 5

Calibrate your throttle pedal. Go to "Tools" -> "Calibrate TPS". Don't touch the throttle and click on "Get Current" next to "Closed Throttle ADC count". Now step on the gas (full-throttle/pedal fully depressed) And do the same for no-throttle (pedal fully released). Burn to ECU.

### Step 6

Test your outputs. Under "Controller" -> "Bench Test & Commands" you can see a lot of options for outputs you can test. Let's focus on the basic ones for now. Spark and Fuel. First, if your car's fuel pump is controlled by the ECU, test "Fuel Pump". You should hear the fuel pump running.

Then move on to spark. Here it depends on how your car is set up. If you have a 4-cylinder with wasted spark (which is likely the majority of users), you will likely be using "Spark #1" and "Spark #3". When you click the test button, you should hear the corresponding ignition coil firing. If you can't hear the spark, you may want to pull a spark plug (or use a spare) and hook it up to the spark plug connector and ground it. Test again and you should see a spark arcing. Dont shock yourself.

Now it's time to test your injectors. Again, this depends on your vehicle. Most cars will at least have two banks of injectors. So you should definitely hear injectors firing when you're testing "Injector #1" and "Injector #2". If you have full-sequential fuel, you should try as many injectors as your engine has cylinders. *Fuel is flammable. Have a fire extinguisher near by just in case.

That's the basic outputs tested. With this you should be able to get the engine to run. You can go ahead and test the other outputs as well. Like Check Engine Light. Engine-Fan, AC, AC-Fan etc.

Close the test window. We're getting close to starting the car.

### Step 7

Turn the ignition off and unplug the USB cable. This removes power to the unit- (just to make sure we're in a defined state). Then reconnect the USB cable, turn on the ignition, wait for TunerStudio to come to life and then crank the engine. You should see the rpms jump to a positive value (typical would be anywhere between 200 and 600rpm) and your engine should start. It may take a few cranks for rpms to register. If you see rpms in Tunerstudio, but the engine isn't starting, keep at it. It may take quite a bit longer than the stock ECU. You are probably used to cranking taking approx. 2s or so. gerEFI takes about 2s of cranking before it can identify the position of the crankshaft. And then it will fire the injectors and ignition coils. It may take it quite a while (>10s which seems like an eternity when cranking) for the engine to catch. Don't give up. There may be coughs and sputters. Play with the throttle a little. It will start eventually. Post your findings to the [forum](https://gerefi.com/forum/) and we can help!

And we're done with the initial startup. Congratulations- you have your car running on your standalone aftermarket ECU! Now the fun really begins :)
