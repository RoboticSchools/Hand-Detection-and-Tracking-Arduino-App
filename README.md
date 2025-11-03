### Microbit Code to Receive the Data from Hand Detection and Tracking App

[Open in MakeCode Editor](https://makecode.microbit.org/_TYEayHArWU2o)

<img width="800" height="600" alt="image" src="https://makecode.microbit.org/_VuaJ1g4iMEMP"/>

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
    int values = sscanf(Serial.readStringUntil('\n').c_str(), "%d,%c,%d", &handCount, &typeChar, &fingerCount);
    if (values == 3) {
      Serial.print("Hands: "); Serial.print(handCount);
      Serial.print(" Type: "); Serial.print(typeChar);
      Serial.print(" Fingers: "); Serial.println(fingerCount);
    }
  }
}
