---
layout: post
permalink: "/ruby/raspberrypi"
title: "Ruby conversion of rpi_gpio"
---
This post is going to be about a ruby gem I found for raspberry pi 3 devices. Most of the raspberry pi 3 users who work on ruby use a gem called [`pi_piper`][pi_piper-github]. For those who have worked on python and used `rpi_gpio` as their main package for controlling I/O pins of the device might find it hard to use `pi_piper`.

This gem [`rpi_gpio`][rpi_gpio-github] is the ruby conversion of [`rpi_gpio`][rpi_gpio-python] python module. It works just like how to python module works and so the syntax is very similar. I'm not very sure whether it can used in big applications because the python module is not suggested to be used in time critical applications. This is because we can't predict when python will be busy collecting garbage. Ruby uses a different garbage collection technique and so this gem might be more efficient.

For example: Code for blinking two LED devices alternatively in the ports 17 and 18 of the raspberry pi 3 device.

Python:
{% highlight ruby %}
import RPi.GPIO as Blink_led

Blink_led.setmode(Blink_led.BCM)
Blink_led.setup(17,Blink_led.OUT)
Blink_led.setup(18,Blink_led.OUT)
for counter in range(0,10):
	Blink_led.output(17,True)
	Blink_led.output(18,False)
	time.sleep(1)
	Blink_led.output(17,False)
	Blink_led.output(18,True)
	time.sleep(1)
Blink_led.output(18,False)
{% endhighlight %}

Ruby:
{% highlight ruby %}
require 'rpi_gpio'

RPi::GPIO.set_numbering :bcm

RPi::GPIO.setup 17, :as => :output
RPi::GPIO.setup 18, :as => :output

10.times do
  RPi::GPIO.set_high 17
  RPi::GPIO.set_low 18
  sleep(1)
  RPi::GPIO.set_low 17
  RPi::GPIO.set_high 18
  sleep(1)
end

RPi::GPIO.set_low 18
{% endhighlight %}

You can download the ruby gem [`here`][rpi_gpio-gem].

[pi_piper-github]: https://github.com/jwhitehorn/pi_piper
[rpi_gpio-gem]: https://rubygems.org/gems/rpi_gpio
[rpi_gpio-github]: https://github.com/ClockVapor/rpi_gpio
[rpi_gpio-python]: https://sourceforge.net/projects/raspberry-gpio-python/
[garbage-collection]: http://patshaughnessy.net/2013/10/24/visualizing-garbage-collection-in-ruby-and-python