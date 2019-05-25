# arduino_servo

#include <Servo.h>

Servo motor_servo;  // 產生servo物件

int pin = 0;  // 類比pin連結至可變電阻
int val;    // 可變電阻讀取到的變數

void setup() {
  motor_servo.attach(7);  // pin7 連至servo motor
}

void loop() {
  val = analogRead(pin);            // (value between 0 and 1023)
  val = map(val, 0, 1023, 0, 180);     //(value between 0 and 180)
  motor_servo.write(val);                  //令 servo motor 位置決定於 val 
  delay(10);                           
}
