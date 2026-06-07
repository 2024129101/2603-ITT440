  ![Logo](apache%20Jmeter.png)


  
# 🚀 Comprehensive Performance Testing and Bottleneck Analysis of a Web Application Using Apache JMeter

---
## 👤 Author Information
* **Name:** AMIRA NATASHA BINTI AMIR
* **Course:** ITT440 NETWORK PROGRAMMING
* **Project:** Comprehensive Web Application Performance Testing & Analysis

---

## 📌 Project Overview
This project focuses on conducting a comprehensive performance evaluation of the target web application:
👉 **[the-internet.herokuapp.com](https://the-internet.herokuapp.com/)**

Using **Apache JMeter**, the application's performance, stability, and scalability were evaluated under various user load conditions through distinct testing methodologies, aiming to uncover hidden system constraints.

---

## 🎯 Objectives
* **Execute Multi-Tier Testing:** Conduct Load, Stress, and Soak testing using Apache JMeter.
* **Metric Evaluation:** Analyze critical KPIs including response time, throughput, latency, and error rates.
* **Identify Bottlenecks:** Detect system limitations, breaking points, and performance degradation causes.
* **Provide Optimization Strategies:** Deliver actionable recommendations for infrastructure and code-level improvements.

---

## 🛠️ Performance Testing Tool

### **Apache JMeter (v5.6.3)**
Apache JMeter was selected as the core testing engine because it is an industry-standard, open-source tool capable of simulating heavy concurrent user behavior and generating high-fidelity analytical reports.

### **Key Advantages**
* 💰 **Cost-Effective:** Free and open-source with extensive community support.
* 📈 **Versatile:** Native support for multiple protocols and performance testing paradigms.
* 🖥️ **User-Centric:** Intuitive GUI for test script development and robust CLI for non-GUI execution.
* 📊 **Reporting:** Generates dynamic, data-rich HTML Dashboard Reports.

🔗 **Official Website:** [Apache JMeter](https://jmeter.apache.org/)

---

## 💻 Test Environment Configuration

The testing was executed within a controlled local environment with the following specifications:

| Component | Specification |
| :--- | :--- |
| **Operating System** | Windows 11 |
| **Processor** | Intel Core i5 |
| **RAM** | 8 GB |
| **Testing Tool** | Apache JMeter 5.6.3 |
| **Java Environment** | JDK 17 |
| **Browser Context** | Google Chrome |
| **Network Profile** | WiFi Connection |

---

## 🧪 Performance Testing Scenarios

### **1. Load Test (Normal Workload)**
* **Objective:** Evaluate how the system handles the normal expected concurrent traffic.
* **Configuration:**
  * **Virtual Users (Threads):** 50
  * **Ramp-Up Period:** 30 Seconds
  * **Loop Count:** Infinite (Controlled by duration)
  * **Duration:** 300 Seconds (5 Minutes)
* **Expected Outcome:** Low response times, high stability, and 0% error rates under basic concurrent user loads.

### **2. Stress Test (Peak Workload)**
* **Objective:** Find the application's breaking point and behavior under sudden heavy traffic conditions.
* **Configuration:**
  * **Virtual Users (Threads):** 500
  * **Ramp-Up Period:** 20 Seconds
  * **Loop Count:** Infinite (Controlled by duration)
  * **Duration:** 300 Seconds (5 Minutes)
* **Expected Outcome:** Spikes in response times, potential server-side instabilities, and noticeable request failures due to extreme load.

### **3. Soak Test (Endurance Workload)**
* **Objective:** Identify memory leaks, resource depletion, and performance degradation over time.
* **Configuration:**
  * **Virtual Users (Threads):** 50
  * **Loop Count:** Infinite (Controlled by duration)
  * **Duration:** 1800 Seconds (30 Minutes)
* **Expected Outcome:** Consistent memory utilization and steady throughput without system degradation over an extended timeline.

---

## 🔄 Test Methodology
1. **Scripting:** Formulate Thread Group structures and define HTTP Request Samplers.
2. **Simulation:** Configure logical pacing, timers, and ramp-up execution states.
3. **Execution:** Run automated suites across Load, Stress, and Soak variations.
4. **Data Collection:** Capture raw performance metrics utilizing JMeter Listeners (`.jtl` logs).
5. **Reporting:** Generate native HTML Dashboard components and aggregate data matrices.
6. **Analysis:** Cross-examine metrics to pinpoint application failure vectors.

---

## 📈 Performance Metrics Analyzed

| Metric | KPI Target | Description |
| :--- | :--- | :--- |
| **Response Time** | `ms` | Total time elapsed from request dispatch to final byte reception. |
| **Throughput** | `req/sec` | The volume of transactions handled by the server per second. |
| **Error Rate** | `%` | The percentage of failed HTTP requests against total requests. |
| **Latency** | `ms` | Network delay before the server starts responding to a request. |
| **Active Threads** | `count` | The number of concurrent virtual users active at any given second. |

---

## ⚠️ Bottleneck Analysis Findings
* **Latency Spikes:** Visible increase in average response times when concurrent traffic scaled past the baseline threshold.
* **Error Influx:** Request failures surfaced under stress execution, potentially indicating server-side connection pooling exhaustion.
* **Rate Limiting:** Trace patterns indicate potential anti-bot policies or strict rate-limiting caps on the hosting infrastructure.
* **Resource Contention:** Fluctuations in throughput stability under sustained loads, hinting at backend or CPU limits.

---

## 💡 Recommendations for Optimization
* ⚖️ **Load Balancing:** Deploy a reverse proxy (e.g., Nginx) or load balancer to distribute user traffic evenly.
* 🗄️ **Query Optimization:** Optimize heavy backend database operations and introduce indexing.
* 💾 **Caching Layer:** Implement Redis or Memcached server-side to cache static content and redundant queries.
* ⚙️ **Resource Scaling:** Increase horizontal/vertical server scaling (RAM/vCPU allocation) during peak seasons.
* 🛡️ **Connection Pooling:** Tune server runtime configurations (e.g., Tomcat/Apache) to handle larger concurrent request pools.

---

## 🏁 Conclusion
Apache JMeter successfully exposed the distinct architectural performance boundaries of the target web application. While the platform demonstrated high reliability and acceptable response curves during the **Load Test**, system bottlenecks and processing thresholds were made evident during the **Stress Test**. Furthermore, the **Soak Test** verified that the platform maintains adequate baseline endurance under prolonged traffic conditions without catastrophic crashes.

---

## 📸 Empirical Evidence & Reports

### 🟩 1. Load Test Results (50 Users / 300s)
<details>
  <summary>📐 Click to see 3 Load Test Screenshots</summary>
  <br>
  
  #### 1. Statistics Matrix
  ![Load Test Statistics](LOAD%20STATISTIC.png) 
  
  #### 2. Response Times Over Time
  ![Load Test Response Time](LOAD%20RESPONSE.png)
  
  #### 3. Transactions Per Second (Throughput)
  ![Load Test TPS](LOAD%20TRANSACTION.png)
</details>

### 🟨 2. Stress Test Results (500 Users / 300s)
<details>
  <summary>📐 Click to see 4 Stress Test Screenshots</summary>
  <br>
  
  #### 1. Statistics Matrix
  ![Stress Test Statistics](STRESS%20STATISTIC.png)
  
  #### 2. Response Times Over Time
  ![Stress Test Response Time](STRESS%20RESPONSE.png)
  
  #### 3. Transactions Per Second (Throughput)
  ![Stress Test TPS](STRESS%20TRANSACTION.png)
  
  #### 4. Identified System Errors & Failure Codes
  ![Stress Test Errors](STRESS%20ERROR.png)
</details>

### 🟦 3. Soak Test Results (50 Users / 30 Mins)
<details>
  <summary>📐 Click to see 3 Soak Test Screenshots</summary>
  <br>
  
  #### 1. Statistics Matrix
  ![Soak Test Statistics](SOAK%20STATISTIC%20.png)
  
  #### 2. Response Times Over Time
  ![Soak Test Response Time](SOAK%20RESPONSE.png)
  
  #### 3. Transactions Per Second (Throughput)
  ![Soak Test TPS](SOAK%20TRANSACTION.png)
</details>

---

## 🎥 Video Presentation
Click the banner below to watch the comprehensive project walkthrough and analysis:

https://youtu.be/BLZh2ZvoXVo
