# Hand Detection and Tracking - Arduino + Micro:Bit App  
### 🔗 Try the App  
👉 [**Open Live App**](https://roboticschools.github.io/Hand-Detection-and-Tracking-App/)  

---

## 📖 Overview  
This project combines **AI-based hand tracking** with **Arduino** and **BBC Micro:Bit** to enable gesture-controlled robotics and electronics — all from your browser!  
The app detects hands and fingers using your computer’s camera and sends the data in real time to **either Arduino (via Web Serial)** or **Micro:Bit (via Web Bluetooth)**.  
No external software or installations needed — just open the link, connect your board, and start controlling your projects with hand gestures.  

---

## ⚙️ Features  
✅ Real-time hand and finger detection using **MediaPipe Hands**  
✅ Works with both **Arduino** and **BBC Micro:Bit**  
✅ Automatically hides the other board’s connect button once connected  
✅ Sends live tracking data through **Serial (Arduino)** or **Bluetooth (Micro:Bit)**  
✅ Simple payload format for easy integration with your own projects  

---

## 📡 Data Format  
The app sends data in this format: 

`<handCount>, <handType>, <fingerCount>`

| Field | Description | Example |
|--------|--------------|----------|
| `handCount` | Number of hands detected | `1` |
| `handType` | L for Left / R for Right | `L` |
| `fingerCount` | Number of fingers up | `3` |

**Example Message:**  
### 1,L,3

➡️ 1 hand detected, Left hand, 3 fingers up  
