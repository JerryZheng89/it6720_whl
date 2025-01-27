# IT6720
![](https://badge.fury.io/py/license.svg)
![LICENSE](https://licensebuttons.net/l/by-nc/4.0/88x31.png)

## IT6720 lib
This package is the library for device IT6720 or IT6721
[IT6720 Product Main Page](https://cdn.itechate.com/en/product/info_128.aspx?itemid=126&lcid=109)


## How to Support

1. Click the **Star** button in the top right corner to show your support.
2. Share it with others who might be interested to help the project gain more attention.
3. Submit your feedback or issues to help us improve the project.

Thank you for your support! With everyone's participation, we can take this project further!

**Note:** Once the Start count is enough, the project will be released as open source, and all the source code will be publicly available on GitHub.

## Product Overview

IT6700 series power supplies are the most economical power supplies, they have the widest voltage and current utilization, one power supply can replace multiple power supplies, widely used in various testing occasions. 
With the capacity of 100W, voltage output of 60V, current output of 5A, they can control the change rates of the voltage and current automatically.
The power ratio can be up to 3 times.
For instance, One IT6720 can subsitute previous 60V*1.6A/32/*3A/20V*5A 3 kinds of models to save your cost.


## package install on-line
```shell
pip install it6720
```

## package install off-line
```shell
# on Macos
pip install it6720-0.1.0-cp311-cp311-macosx_10_9_universal2.whl

# on Windows
pip install it6720-0.1.0-cp311-cp311-win_amd64.whl

# on Linux
pip install it6720-0.1.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl
```



## Basic Usage
```python
from it6720 import IT6720

if __name__ == "__main__":
    it6700 = IT6720("/dev/ttyUSB0")
    if it6700.open():
        print("set work mode to remote controll")
        it6700.set_work_mode('remote')
        it6700.set_voltage_max(5.0)
        it6700.set_out_voltage(3.3) # set voltage 3.3V
        it6700.set_out_current(0.888) # set current 0.888A
        it6700.set_ouput_mode('on')
        time.sleep(3)
        print("------------ local -------------")
        it6700.read_dev_status()
        it6700.set_work_mode('local')
        it6700.set_ouput_mode('off')
        it6700.close()
        print("it6700 series closed!")
    else:
        print(f"open serial port:{opat_port} failed!")
```
