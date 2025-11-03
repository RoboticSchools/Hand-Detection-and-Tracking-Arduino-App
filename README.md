### Microbit Code to Receive the Data from Hand Detection and Tracking App

[Open in MakeCode Editor](https://makecode.microbit.org/_EpK9fHgF2Wa1)

<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/872759e1-c76b-4887-a323-655ddf2b9159" />

---

### Arduino Code to Receive the Data from Hand Detection and Tracking App

```cpp
int handCount;
char typeChar;
int fingerCount;

void setup() {
  Serial.begin(115200);
}

void loop() {
  if (Serial.available()) {
    sscanf(Serial.readStringUntil('\n').c_str(), "%d,%c,%d", &handCount, &typeChar, &fingerCount);

    Serial.print("Hands: "); Serial.print(handCount);
    Serial.print(" Type: "); Serial.print(typeChar);
    Serial.print(" Fingers: "); Serial.println(fingerCount);
  }
}
```
