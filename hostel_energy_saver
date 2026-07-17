#define PIR_PIN 13
#define TEMP_PIN 34
#define LIGHT_RELAY 26
#define FAN_RELAY 27

void setup() {
  pinMode(PIR_PIN, INPUT);
  pinMode(LIGHT_RELAY, OUTPUT);
  pinMode(FAN_RELAY, OUTPUT);

  Serial.begin(9600);
}

void loop() {
  int motion = digitalRead(PIR_PIN);
  int temp = analogRead(TEMP_PIN);

  // Occupancy Detection
  if (motion == HIGH) {
    digitalWrite(LIGHT_RELAY, HIGH);
    Serial.println("Person Detected - Lights ON");
  } else {
    digitalWrite(LIGHT_RELAY, LOW);
    Serial.println("No Person - Lights OFF");
  }

  // Temperature-based Fan Control
  if (temp > 2000) {
    digitalWrite(FAN_RELAY, HIGH);
    Serial.println("Fan ON");
  } else {
    digitalWrite(FAN_RELAY, LOW);
    Serial.println("Fan OFF");
  }

  delay(1000);
}
