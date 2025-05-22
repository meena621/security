const int pirPin = 2;       // PIR sensor output pin
const int ledPin = 13;      // LED pin
const int buzzerPin = 8;    // Buzzer pin

void setup() {
  pinMode(pirPin, INPUT);
  pinMode(ledPin, OUTPUT);
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int motionDetected = digitalRead(pirPin);
  
  if (motionDetected == HIGH) {
    digitalWrite(ledPin, HIGH);
    digitalWrite(buzzerPin, HIGH);
    Serial.println("Motion Detected!");
    delay(1000); // Alarm duration
  } else {
    digitalWrite(ledPin, LOW);
    digitalWrite(buzzerPin, LOW);
  }
}
