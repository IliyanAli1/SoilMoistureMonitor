#include <SPI.h>
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>
#define OLED_RESET 4 
Adafruit_SSD1306 display(OLED_RESET);
//SDA-A4
//SCK-A5

const int sensorPin = A0; 
const int redPin = 7;
const int greenPin = 5;
const int threshold = 4000;


void setup() {
  // put your setup code here, to run once:
  display.begin(SSD1306_SWITCHCAPVCC, 0x3C);
  display.clearDisplay();
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  display.setTextSize(2);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.clearDisplay();

    int sensorValue = analogRead(sensorPin);
  Serial.print("Sensor value: ");
  Serial.println(sensorValue);

  if(sensorValue > threshold) {
    digitalWrite(redPin, HIGH);
    digitalWrite(greenPin, LOW);
    display.println("Not enough water");
  }
  else {
    digitalWrite(redPin, LOW);
    digitalWrite(greenPin, HIGH);
    display.println("Enough    water");
  }
  delay(10);

  display.display();
}
