### Arduino Code to Receive the Data from Hand Detection and Tracking App

```C++

int handCount;
char typeChar;
int fingerCount;

void setup() {
  Serial.begin(115200);
}

void loop() {
  if (Serial.available()) {
    int values = sscanf(Serial.readStringUntil('\n').c_str(), "%d,%c,%d", &handCount, &typeChar, &fingerCount);
    if (values == 3) {
      Serial.print("Hands: "); Serial.print(handCount);
      Serial.print(" Type: "); Serial.print(typeChar);
      Serial.print(" Fingers: "); Serial.println(fingerCount);
    }
  }
}

```


<img width="1061" height="607" alt="image" src="https://github.com/user-attachments/assets/3ed6b043-e75c-47f5-897a-0fe959293337" />
