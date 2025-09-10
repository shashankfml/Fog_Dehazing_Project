# Fog_Dehazing_Project

# Vision-Based Fog & Extreme Weather Perception System

## 🌫️ Motivation
Adverse weather conditions such as **dense fog, snow, and low visibility** severely impact transportation safety and defense operations.  
- In **urban mobility and autonomous driving**, fog drastically reduces the reliability of computer vision systems.  
- In **Indian Railways**, dense winter fog in **Delhi, Punjab, Haryana, and Uttar Pradesh** disrupts thousands of train services annually.  
- In **extreme terrains like Kashmir and the Northeast**, soldiers face reduced visibility in snowstorms and fog, affecting convoy safety and surveillance.  

This project unifies **state-of-the-art research on vision under foggy conditions** with **real-world deployment needs of Indian Railways and defense logistics**.  

---

## 1️⃣ Literature from Computer Vision Research

Research led by **Christos Sakaridis (ETH Zurich)** has been pivotal in addressing perception under fog:

- **Semantic Foggy Scene Understanding (2018, IJCV):**  
  - Introduced **Foggy Cityscapes** (20k synthetic foggy images) and **Foggy Driving** (real foggy dataset).  
  - Demonstrated that **semi-supervised learning** with synthetic + real fog improves semantic segmentation and detection.  
  - Key insight: *Dehazing alone is insufficient — models must learn directly under fog conditions.*

- **Curriculum Model Adaptation (CMAda, 2019):**  
  - Proposed gradual adaptation from **light synthetic fog → dense real fog**.  
  - Released **Foggy Zurich** dataset (~3.8k real foggy images).  
  - Key insight: Curriculum learning with fog density estimation helps models generalize better in real fog.

- **Foggy Synscapes (2019):**  
  - Fully synthetic dataset (25k high-quality foggy scenes).  
  - Showed that **purely synthetic fog data** can outperform partially synthetic approaches when adapting to real fog.  
  - Key insight: Large-scale synthetic fog datasets are powerful for training robust perception models.

**Takeaway for us:**  
- Pure RGB dehazing is not enough.  
- **Synthetic + real fog datasets, curriculum adaptation, and multimodal fusion** are the most reliable strategies for perception under fog.  

---

## 2️⃣ Extreme Weather Challenges in India

### **Railways (Dense Fog in the North)**
- **Regions:** Delhi, Uttar Pradesh, Punjab, Bihar — among the most fog-affected globally.  
- **Current Solutions:**  
  - *Detonators, manual signaling, speed restrictions* (historical).  
  - *FogPASS (GPS-based alerts)* → helps with fixed landmarks but **cannot detect dynamic hazards**.  
  - *Kavach 4.0 (ATP system)* → prevents collisions and SPADs, but does **not solve visibility for loco pilots**.  
- **Operational Gap:** No current system can provide **real-time obstacle detection under fog**.

### **Military Operations (Kashmir & Northeast)**
- **Scenarios:**  
  - Convoys in mountain passes with fog/snow.  
  - Border patrols in whiteout/blizzard conditions.  
  - UAV/ground robot navigation in low visibility.  
- **Current Issues:**  
  - Conventional vision sensors fail in fog/snow.  
  - Thermal cameras help but lack depth.  
  - Radar is robust but low-resolution.  
- **Operational Gap:** Need for **multimodal perception (Radar + LiDAR + Thermal)** for robust navigation and surveillance.

---

## 3️⃣ Proposed Multimodal Fog Dehazing System

### 🔍 Core Idea
Develop a **vision system for extreme weather** that integrates **Radar, LiDAR, and Thermal Imaging** with AI-driven sensor fusion and 3D reconstruction.  

### 🎯 Objectives
- **Railways:** Real-time detection of obstacles (animals, humans, broken tracks) under dense fog.  
- **Military:** Robust situational awareness for convoys, UAVs, and border patrol in low visibility.  
- **Vision Research:** Contribute datasets and benchmarks for foggy scene understanding in real-world scenarios.  

### 🏗️ System Architecture
1. **Sensors**
   - Long-range mmWave **Radar** (robust in fog/snow).  
   - **LiDAR** (fog-tuned for medium-range 3D geometry).  
   - **Thermal Cameras** (detect humans/animals in low-visibility).  
   - Auxiliary **RGB Cameras** (clear weather only).  

2. **Processing Pipeline**
   - Physics-based **fog density estimation** (adapted from CMAda).  
   - **Multimodal sensor fusion** (Radar + LiDAR + Thermal).  
   - **3D reconstruction** of scene with uncertainty modeling.  
   - AI-driven **object detection & tracking** under fog.  

3. **Outputs**
   - **Railways HMI:** Minimalist audio + visual alerts for loco pilots.  
   - **Military HMI:** AR overlays, thermal-augmented feeds, convoy guidance.  
   - **Data logs:** Geo-tagged obstacle detection for analytics and training.  

---

## 4️⃣ Relation to Kavach 4.0 (Indian Railways)

- **Kavach 4.0:** Automatic Train Protection (ATP) preventing SPADs and collisions.  
- **Our System:** A **complementary perception layer** that provides obstacle awareness in fog.  
- **Integration Path:**  
  - *Phase 1:* Advisory-only system for pilots.  
  - *Phase 2:* Integration with Kavach’s data layer (after RDSO certification).  
  - *Phase 3:* Automated hazard-aware braking (long-term).  

---

## 5️⃣ Roadmap

1. **Dataset Curation**
   - Combine Foggy Cityscapes, Foggy Zurich, Foggy Synscapes with **Indian railway fog imagery** (Delhi–Lucknow corridor).  
   - Collect **thermal + radar datasets** from railway/military test sections.  

2. **Simulation & Bench Testing**
   - Fog chambers for sensor evaluation.  
   - Curriculum adaptation for model robustness.  

3. **Field Trials**
   - Pilot trials in **Delhi fog belt** (railways).  
   - Convoy navigation experiments in **Kashmir passes** (defense).  

4. **Integration**
   - Connect outputs to **FogPASS-like GPS systems**.  
   - Engage with **RDSO/IRISET** for certification.  
   - Explore **dual-use deployment** (rail + defense).  

---

## 📖 References
- **Christos Sakaridis et al.**  
  - *Semantic Foggy Scene Understanding with Synthetic Data* (IJCV 2018)  
  - *Curriculum Model Adaptation for Foggy Scene Understanding* (2019)  
  - *Foggy Synscapes: Purely Synthetic Fog Data* (2019)  
- **Indian Railways**  
  - RDSO/SPN/201: *FogPASS Specification* (2014)  
  - Kavach 4.0 deployment reports  
- **Global Defense/Mobility Research**  
  - Sensor fusion for autonomous driving in fog  
  - Radar + thermal navigation in defense operations  

---

## 🚆🎖️ Conclusion
Fog and snow degrade not only **computer vision algorithms** but also **real-world railway and military operations**.  

- **From Vision Research:** Synthetic + real fog datasets, curriculum learning, and sensor fusion are the most effective strategies.  
- **For Indian Railways:** Our system complements FogPASS and Kavach by adding **dynamic obstacle perception**.  
- **For Defense:** Enables convoy and UAV navigation in extreme weather.  

This project is a step toward **unified multimodal perception under extreme weather** — bridging **research and deployment** for safer mobility and defense in India.
