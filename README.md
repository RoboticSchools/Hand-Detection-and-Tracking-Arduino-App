# Hand Detection and Tracking — Arduino App

### 🔗 Try the App  
👉 [Open Live App](https://roboticschools.github.io/Hand-Detection-and-Tracking-Arduino-App/)

---

## 📖 Overview  
This project uses a **web-based hand tracking app** that detects hands and fingers using your computer’s camera.  
The detected data is sent to **Arduino via Serial** for gesture-based control of LEDs, motors, or robots.  

It’s simple — no extra software needed. Just open the link, connect your Arduino, and start controlling!

---

## 📡 Data Format  

The app sends data in this format:
<handCount>,<handType>,<fingerCount>


| Field | Description | Example |
|--------|--------------|----------|
| `handCount` | Number of hands detected | `1` |
| `handType` | L for Left / R for Right | `L` |
| `fingerCount` | Number of fingers up | `3` |

**Example Message:**  
`1,L,3` → 1 hand detected, Left hand, 3 fingers up

---

## 💻 Arduino Code
```cpp
String incomingData;
int handCount;
char handType;
int fingerCount;

void setup() {
  Serial.begin(115200);
}

void loop() {
  if (Serial.available()) {
    incomingData = Serial.readStringUntil('\n');
    incomingData.trim();
    sscanf(incomingData.c_str(), "%d,%c,%d", &handCount, &handType, &fingerCount);

    Serial.print("Hands: "); Serial.print(handCount);
    Serial.print(" | Type: "); Serial.print(handType);
    Serial.print(" | Fingers: "); Serial.println(fingerCount);
  }
}


## ⚙️ How to Use

1. Open the web app using the link above.  
2. Allow camera access in your browser.  
3. Connect Arduino to your computer (**use 115200 baud**).  
4. Open Serial Monitor and watch live hand tracking data.  
5. Use the data to trigger LEDs, motors, or any custom logic.
