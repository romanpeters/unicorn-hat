### Waveshare Hat
Modification of the [pimoroni/unicorn-hat](https://github.com/pimoroni/unicorn-hat) library to work with the Waveshare RGB LED Hat (B).

```
import unicornhat as unicorn

unicorn.set_layout(unicorn.WAVEB)
```  

<br><br><br>

pimoroni/unicorn-hat README.md:

--------------------

![Unicorn HAT/pHAT](unicorn-hat-logo.png)

Available from Pimoroni:  
http://shop.pimoroni.com/products/unicorn-hat  
http://shop.pimoroni.com/products/unicorn-phat

### Important Notice

Because Unicorn HAT uses the PWM hardware, which is also how your Raspberry Pi generates analog audio, you may see random colour patterns and flickering.

If this happens, you should add the following to your `/boot/config.txt`:

```
hdmi_force_hotplug=1
```

Sound will work fine using speakers on, for example, an HDMI TV, but you will not be able to use your Pi's 3.5mm audio jack in conjunction with Unicorn HAT.

### `unicornhat` Python Library & Examples

Here you'll find everything you need to start lighting up your Unicorn HAT or pHAT using python.

Python users should probably ignore most of this repository and just:

**Full install ( recommended ):**

```bash
curl -sS https://get.pimoroni.com/unicornhat | bash
```

**Install for Python 3:**

```bash
sudo apt-get install python3-pip python3-dev
sudo pip3 install unicornhat
```

**Install for Python 2:**

```bash
sudo apt-get install python-pip python-dev
sudo pip install unicornhat
```

**Install from GitHub**

Note this library requires the rpi_ws281x Python library which you can find here: https://github.com/pimoroni/rpi_ws281x-python

```
git clone https://github.com/pimoroni/unicorn-hat
cd unicorn-hat/library/UnicornHat
sudo python setup.py install
cd ../..
```

Then proceed to [examples](examples).

### Using with idle/idle3:

`unicornhat` needs root access to function. Please make sure you start LXTerminal and run idle or idle3 with the "sudo" command like so:

```bash
sudo idle
```

### Error Codes

Sometimes Unicorn HAT may fail with an error code, this table details some of the places to look for answers in specific cases:

* -1 Generic failure
* -2 Out of memory
* -3 Hardware revision is not supported - **see: https://github.com/pimoroni/unicorn-hat/issues/70**
* -4 Memory lock failed
* -5 mmap() failed - **you probably forgot to run your code as root, use `sudo python yourcode.py`**
* -6 Unable to map registers into userspace
* -7 Unable to initialize GPIO
* -8 Unable to initialize PWM"
* -9 Failed to create mailbox device
* -10 DMA error
* -11 Selected GPIO not possible
* -12 Unable to initialize PCM
* -13 Unable to initialize SPI
* -14 SPI transfer error

### Documentation & Support

* Getting started - https://learn.pimoroni.com/tutorial/unicorn-hat/getting-started-with-unicorn-hat
* Function reference - http://docs.pimoroni.com/unicornhat/
* GPIO Pinout - http://pinout.xyz/pinout/unicorn_hat, http://pinout.xyz/pinout/unicorn_phat
* Get help - http://forums.pimoroni.com/c/support

### Based Upon rpi_ws281x

`unicornhat` is based upon a modified, Pi 2/3 compatible version of the RPi ws281x Library by Jeremy Garff.

The library was modified by Richard Hirst.

* Modified version: https://github.com/richardghirst/rpi_ws281x
* Original: https://github.com/jgarff/rpi_ws281x

### RaspberryPi-NeoPixel-WS2812

Note: `unicornhat` is no longer based upon this library, but this information is included for posterity.

`unicornhat` was previously based upon a modified version of the ws2812 C driver from: https://github.com/626Pilot/RaspberryPi-NeoPixel-WS2812
