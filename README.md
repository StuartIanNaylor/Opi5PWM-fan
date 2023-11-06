# Opi5PWM-fan
Rockchip pwm output on pin 8
`overlays=rk3588-pwm15-m2`

Only thing if anyone can concur is the 25000000 period 25kHz? :)
Assuming milliseconds prob isn't best but seems to work well.

./fan-speed after making the above change to /boot/firmware/ubuntuEnv.txt
You should have PWM output on pin8 which is close to a 5v& gnd, often where fans are powered.

Will create a service and install...

./log-temp shows temp and fan speed 
