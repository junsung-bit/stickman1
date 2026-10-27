# Custom Character 구현
## 연결도
<img width="1547" height="602" alt="image" src="https://github.com/user-attachments/assets/f1875cd4-1ab0-40ce-a635-b69fd1a44ccc" />

## 스케치
점프하는 스틱맨 캐릭터를 구현하고 싶어서 아래와 같은 스케치를 만들었다.

#include <Wire.h>
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27, 16, 2);

byte man1[8] = {B01110, B01110, B00100, B01111, B10100, B01010, B10001, B10001};
byte man2[8] = {B01110, B01110, B00100, B01110, B10101, B00100, B01010, B01010};
byte man3[8] = {B01110, B01110, B00100, B11110, B00101, B01010, B10001, B10001};

void setup() {
  lcd.init();
  lcd.backlight();
  lcd.createChar(0, man1);
  lcd.createChar(1, man2);
  lcd.createChar(2, man3);
}

void loop() {
  lcd.setCursor(0, 0);
  lcd.write(0);
  delay(150);

  lcd.setCursor(0, 0);
  lcd.write(1);
  delay(150);

  lcd.setCursor(0, 0);
  lcd.write(2);
  delay(150);

  lcd.setCursor(0, 0);
  lcd.write(1);
  delay(150);
}

## 데모

https://github.com/user-attachments/assets/be9c09c6-2f6d-44b8-9e16-01eca262705e


