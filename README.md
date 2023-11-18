# Opi5PWM-fan
Rockchip pwm output on pin 8
`overlays=rk3588-pwm15-m2`

Only thing if anyone can concur is the 40000 period 25kHz? :)
Assuming milliseconds prob isn't best but seems to work well.

./fan-speed after making the above change to /boot/firmware/ubuntuEnv.txt
You should have PWM output on pin8 which is close to a 5v& gnd, often where fans are powered.
Fan speed should be run as root for service. `sudo -i`

Will create a service and install...

./log-temp shows temp and fan speed 

`chmod a+x ./fan-speed ./log-temp`

Cool down
```
stuart@stuart-desktop:~$ ./log-temp
23:26:10 Temp:54538 Fan speed:66%
23:26:11 Temp:54538 Fan speed:64%
23:26:12 Temp:53615 Fan speed:66%
23:26:13 Temp:54538 Fan speed:66%
23:26:15 Temp:45307 Fan speed:46%
23:26:17 Temp:43461 Fan speed:43%
23:26:19 Temp:42538 Fan speed:38%
23:26:23 Temp:41615 Fan speed:38%
23:26:27 Temp:41615 Fan speed:38%
23:26:31 Temp:40692 Fan speed:37%
23:26:39 Temp:40692 Fan speed:37%
23:26:47 Temp:39769 Fan speed:34%
23:26:55 Temp:39769 Fan speed:34%
23:27:11 Temp:39769 Fan speed:34%
23:27:27 Temp:38846 Fan speed:32%
23:27:43 Temp:38846 Fan speed:32%
23:28:15 Temp:37923 Fan speed:31%
23:28:47 Temp:37923 Fan speed:28%
23:29:19 Temp:36076 Fan speed:28%
23:30:23 Temp:35153 Fan speed:27%
23:31:27 Temp:35153 Fan speed:0%
23:32:31 Temp:34230 Fan speed:0%
23:34:39 Temp:32384 Fan speed:0%
```
Heat up
```
stuart@stuart-desktop:~$ ./log-temp
21:53:34 Temp:34230 Fan speed:0%
21:53:36 Temp:36076 Fan speed:0%
21:53:37 Temp:43461 Fan speed:38%
21:53:38 Temp:44384 Fan speed:44%
21:53:40 Temp:46230 Fan speed:49%
21:53:42 Temp:46230 Fan speed:49%
21:53:44 Temp:46230 Fan speed:49%
21:53:48 Temp:46230 Fan speed:49%
21:53:52 Temp:46230 Fan speed:49%
21:53:56 Temp:47153 Fan speed:50%
21:54:04 Temp:48076 Fan speed:50%
21:54:12 Temp:47153 Fan speed:50%
21:54:20 Temp:48076 Fan speed:52%
21:54:36 Temp:49000 Fan speed:55%
21:54:52 Temp:49000 Fan speed:55%
21:55:08 Temp:49923 Fan speed:56%
21:55:40 Temp:51769 Fan speed:58%
21:56:12 Temp:50846 Fan speed:58%
21:56:44 Temp:52692 Fan speed:62%
21:57:48 Temp:52692 Fan speed:64%
21:58:52 Temp:54538 Fan speed:64%
21:59:56 Temp:54538 Fan speed:66%
22:02:04 Temp:54538 Fan speed:66%
22:04:12 Temp:54538 Fan speed:66%
22:06:20 Temp:54538 Fan speed:64%
22:10:20 Temp:55461 Fan speed:68%
22:14:20 Temp:55461 Fan speed:68%
22:18:20 Temp:55461 Fan speed:68%
22:22:20 Temp:56384 Fan speed:70%
22:26:20 Temp:55461 Fan speed:68%
22:30:20 Temp:55461 Fan speed:68%
```
The armour shell for the pi5 as it comes is near useless but after some mods it never throttles @ 100% load tested for well over 30 minutes as it does inch up slowly.

Personally get one of the 3 pin fans from pi hut so its software controller and stops on shutdown and in idle is not needed.
https://thepihut.com/products/software-controllable-5v-30mm-fan-for-raspberry-pi

The fan as it comes is constricted as it lies flat on the metal base and has no space to blow through.
The screws supplied means you can use some m3 bolts as spacers to give an air gap.
Then the next thing as thermal pads are not as soft as you think and the pcb is very thin I think it warps slightly and in the middle at the cpu its worse.
Get a 3mm thermal pad and place between the backplate and CPU as well as applying oppisite pressure the backplate also cools.

After that you get a pretty might compact armor case cooler that is software controlled.
