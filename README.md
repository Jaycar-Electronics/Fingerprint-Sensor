# Jaycar Fingerprint Sensor

This module has been changed to work with the Adafruit Fingerprint Sensor Library [on Github](https://github.com/adafruit/Adafruit-Fingerprint-Sensor-Library).

You can install this in the Arduino IDE by clicking:

```plaintext
Sketch->Include Library->Manage Libraries
```

And installing the Adafruit Fingerprint Sensor Library.

The fingerprint sensor is completely blank, and as such any checks to `verifyPassword()` or fingerprint identification will fail;

If you are using the module for the first time, set as such:

```cpp
uint8_t p = finger.setPassword(0); //password as 32bit int
if (p == FINGERPRINT_OK) {
    Serial.println("OK"); // Password is set
}
```

This will allow `verifyPassword` to succeed, you should also use the `Enroll` example to add your first fingerprint, which will allow fingerprint tests to succeed or fail later.

## Pin out

|Pin | Function |
| --- | ---- |
| 1 | Touch sensor input ( 3.3V )
| 2 | Touch sensor output
| 3 | VCC in (3.3V)
| 4 | Serial UART TX (rx on arduino)
| 5 | Serial UART RX (tx on arduino)
| 6 | Ground

The Adafruit library uses `SoftwareSerial` on pins 2 and 3, which make for an easy connection on the arduino. (2 for RX, connected to Sensor TX, and vice versa).
