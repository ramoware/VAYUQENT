# VAYUQENT — The Q-Sentinel That Never Sleeps

> **VAYU (Sanskrit: Life-Breath) + QENT (Q-Sentinel): A contactless respiratory guardian that watches breath using WiFi.**

**Tagline: No wires. No touch. No false alarms. Just breath.**

VAYUQENT is a contactless respiratory Digital Twin system that turns any low-cost WiFi chip into a medical-grade apnea monitor. No wearables, no cameras, no expensive ventilators. Just the WiFi you already have.

---

### The Problem We Solve

Current continuous respiratory monitors have two failures:

1.  **Too expensive** for low-resource and rural hospitals
2.  **Too fragile** — edge sensors trigger frequent false alarms when a patient moves, shifting a body looks like breathing.

In an ICU/NICU, a false alarm is not an annoyance. It's alarm fatigue that costs lives.

### Introducing VAYUQENT: Q-Factor Obstructive Response Alert

VAYUQENT is the world's first **Q-Sentinel**. Instead of treating WiFi signals as abstract images, we teach physics to the neural network.

**How it works:**

**1. WiFi CSI Sensing:** We monitor WiFi Channel State Information (CSI). Your chest moving changes the Q-Factor (Quality Factor) of the WiFi signal. We capture that on 50+ subcarriers, in real-time, with Unix Epoch timestamps.

**2. PINN on Edge - No Cloud, No Lag:** State-of-the-art systems use CNN + LSTM models that need desktop GPUs and large time buffers. This creates dangerous latency.

VAYUQENT implements a **Physics-Informed Neural Network (PINN)** compiled via piecewise non-linear approximation to run directly on an **ultra-low-cost ESP32 microcontroller** — not an FPGA, not a Raspberry Pi 4. It builds a live digital twin of Volume and Pressure.

**3. Physics Gate Artifact Rejection:** This is our breakthrough. Old systems use only frequency — so motion *looks* like breathing.

VAYUQENT uses quantitative volume + pressure validation. If the physics doesn't add up, it's rejected automatically.

> **Result: 13.2% automatic artifact rejection. Zero post-processing window. Real-time.**

**BEFORE (Standard CSI):** Body shift = 40+ spikes = False apnea alarm.
**AFTER (VAYUQENT):** Body shift = Rejected by Physics Gate. Valid breaths = Black dots. Clean breathing continues.

---

### Why VAYUQENT Wins

| Feature | Standard Devices / BreatheSmart, CNN+LSTM | VAYUQENT |
| :--- | :--- | :--- |
| **Cost** | $3000+ ventilator or $150+ FPGA/RPi4 | **<$15 ESP32** - Built for Bharat and low-resource hospitals |
| **Contact** | Wearable / Belt / Camera (Privacy risk) | **100% Contactless** - No touch, no infection, no camera |
| **Intelligence** | Treats RF as abstract image | **Physics-Informed Multi-Task** - Aligns RF with real bio-mechanics |
| **Latency** | Needs large buffers, GPU | **Real-time on Edge** - No dangerous operational delay |
| **False Alarms** | Motion = Breath | **Quantitative Gate** - Volume/Pressure must obey physics |

### Built For

- **Rural & Low-Resource Hospitals:** Where a $3000 monitor is not an option
- **NICU / ICU:** Where every false alarm creates fatigue
- **Home Care:** For sleep apnea patients who won't wear a device to sleep
- **Elderly Care:** Dignified, private monitoring without a camera in the bedroom

### The Tech Stack

- **Sensing:** WiFi CSI on ESP32 (SC_12 filtered best)
- **Core:** PINN Digital Twin (Volume + Pressure)
- **Edge Compilation:** HDL / Piece-wise non-linear approximation for microcontrollers
- **Alerting:** Q-Factor Obstructive Response Alert (QENT)

### Etymology & Brand Promise

**VAYUQENT** is a coined word to own the future of breath.

- **VAYU:** Sanskrit for life-breath, air, the first thing we do and last we do.
- **QENT:** Q-Sentinel. Q = Q-Factor of WiFi CSI, ENT = Sentinel - the soldier who never sleeps.

Search `VAYUQENT` anywhere in the world. Only we exist. That is how unique our promise is.

**Numerology:** VAYUQENT = 3 - The number of communication and alerting. Exactly what a sentinel must do.

### Roadmap

- [x] Phase 1: ESP32 CSI capture + Physics Gate (13.2% rejection proven)
- [ ] Phase 2: Clinical validation for apnea alert latency < 2s
- [ ] Phase 3: VAYUQENT Box - Plug-and-play router that is a sentinel
- [ ] Phase 4: VAYURAQ Score - Our own Respiratory Alert Quotient to replace AHI

### References & Inspiration

Built on the shoulders of:
- Zhang et al., Implementation of PINN on Edge Device, MCSoC 2023
- Mosleh et al., Monitoring Respiratory Motion With Wi-Fi CSI: BreatheSmart Algorithm, IEEE Access 2022
- Guo et al., Contactless abnormal respiration monitoring via CSI ratio map, Measurement 2026

---

**VAYUQENT — The Q-Sentinel That Never Sleeps.**

> Contact: Pranitajagtap and ramoware
> Status: Research Prototype | Seeking Clinical Partners

*No wires. No touch. Just the breath that watches over breath.*
