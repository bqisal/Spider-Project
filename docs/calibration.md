**we put our legs back into the starting position**

using code:
```cpp
#include <Wire.h>
#include <Adafruit_PWMServoDriver.h>

Adafruit_PWMServoDriver pwm = Adafruit_PWMServoDriver(0x40);

int angleToPulse(int angle) {
  return map(angle, 0, 180, 102, 512);
}

// соответствует номерам 2..13
int servoChan[12] = {
  0,  // 2
  1,  // 3
  2,  // 4
  3,  // 5
  4,  // 6
  5,  // 7
  6,  // 8
  7,  // 9
  8,  // 10
  9,  // 11
  10, // 12
  11  // 13
};

void setup() {
  pwm.begin();
  pwm.setPWMFreq(50);
  delay(10);

  // Все в 90°
  for (int i = 0; i < 12; i++) {
    pwm.setPWM(servoChan[i], 0, angleToPulse(90));
    delay(50);
  }
}
```



**Photo of spider which had starting position**

![photo_2025-12-07_16-56-24](https://github.com/user-attachments/assets/02a4cc72-3235-4011-99c8-3612fb1c2030)


void loop() {}
//код для калибровки


