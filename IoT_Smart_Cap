#define trigPin 2
#define echoPin 3
#define buzzerPin 4

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  long duration, distance;
  
  // Send an ultrasonic pulse to measure distance
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  // Measure the time it takes for the pulse to return
  duration = pulseIn(echoPin, HIGH);
  
  // Calculate distance in centimeters
  distance = (duration / 2) / 29.1;
  
  // Check the distance
  if (distance < 40) {
    // If an obstacle is detected within 20cm, sound the buzzer
    digitalWrite(buzzerPin, HIGH);
    delay(500);  // Buzzer on for half a second
    digitalWrite(buzzerPin, LOW);
  }

  // Print the distance to the serial monitor for debugging
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  delay(100);  // Wait for a short time before the next measurement
}
