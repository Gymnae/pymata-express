# Retrieving The Latest Input Data Values
As was mentioned earlier, 
[callbacks](../polling/#using-callbacks-instead-of-polling) are preferred over 
polling for input data change notifications.

That being said, your application may dictate using polling over callbacks. This section
describes the API methods to retrieve the latest cached input data values.

## analog_read
```python
 async def analog_read(self, pin)

    Retrieve the last data update for the specified analog pin.

    :param pin: Analog pin number (ex. A2 is specified as 2)

    :returns: [last value reported, time-stamp]
```

**Examples:**

1. [analog_input_with_time_stamps.py](https://github.com/MrYsLab/pymata-express/blob/master/examples/analog_input_with_time_stamps.py)
2. [analog_input_with_time_stamps_oo.py](https://github.com/MrYsLab/pymata-express/blob/master/examples/analog_input_with_time_stamps_oo.py)

## dht_read
```python
def dht_read(self, pin):
    """
    Retrieve the last data update for the specified dht pin.

    :param pin: digital pin number

    :return: A list = [humidity, temperature  time_stamp]

             ERROR CODES: If either humidity or temperature value:
                          == -1 Configuration Error
                          == -2 Checksum Error
                          == -3 Timeout Error

    """
```
**Examples:**

1. [dht.py](https://github.com/MrYsLab/pymata-express/blob/master/examples/dht.py)


## digital_read
```python
 async def digital_read(self, pin)

    Retrieve the last data update for the specified digital pin.

    :param pin: Digital pin number

    :returns: [last value reported, time-stamp]

``` 
**Examples:**

1. [digital_input.py](https://github.com/MrYsLab/pymata-express/blob/master/examples/digital_input.py)
2. [digital_input_debounce.py](https://github.com/MrYsLab/pymata-express/blob/master/examples/digital_input_debounce.py)
3. [digital_input_pullup.py](https://github.com/MrYsLab/pymata-express/blob/master/examples/digital_input_pullup.py) 

## i2c_read_saved_data
```python
 async def i2c_read_saved_data(self, address)

    This method retrieves cached i2c data to support a polling mode.

    :param address: I2C device address

    :returns data: [raw data returned from i2c device, time-stamp]
```

**Example:**

1. [i2c_adxl345_accelerometer.py](https://github.com/MrYsLab/pymata-express/blob/master/examples/i2c_adxl345_accelerometer.py)


## sonar_read
```python
 async def sonar_read(self, trigger_pin)

    This is a FirmataExpress feature

    Retrieve Ping (HC-SR04 type) data. The data is presented as a dictionary.

    The 'key' is the trigger pin specified in sonar_config() and the 'data' is the current measured distance (in centimeters) for that pin. If there is no data, the value is set to None.

    :param trigger_pin: key into sonar data map

    :returns: [last distance, raw time stamp]
```
**Example:**
1. [hc-sr04_distance_sensor.py](https://github.com/MrYsLab/pymata-express/blob/master/examples/hc-sr04_distance_sensor.py)


<br>
<br>
Copyright (C) 2020 Alan Yorinks. All Rights Reserved.
