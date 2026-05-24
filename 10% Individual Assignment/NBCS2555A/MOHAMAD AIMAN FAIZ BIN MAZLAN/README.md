# MOHAMAD AIMAN FAIZ BIN MAZLAN

---

# 🚀 Performance Evaluation of HTTP Response Behavior Under Concurrent Load Using k6

---

## 🎓 ITT440 – Network Programming (Individual Assignment)

| Item | Details |
|------|--------|
| **Name** | MOHAMAD AIMAN FAIZ BIN MAZLAN |
| **Student No** | 2024369211 |
| **Course** | ITT440 – Network Programming |
| **Target API** | https://httpbin.org/ |
| **Tools Used** | k6, Grafana, InfluxDB, Docker |

---

# 1. Project Overview

This project focuses on testing how an API behaves under different levels of traffic using **k6 performance testing tool**.

Instead of only checking whether the API works, this project evaluates how it performs under:
- Normal usage
- High concurrent load
- Server error conditions

The results are collected using **InfluxDB** and visualized using **Grafana dashboards**.

---

# 2. Objective

The main objective of this project is to understand how HTTP responses behave when multiple users access the system at the same time.

More specifically, this project aims to:
- Measure response time under load  
- Observe throughput changes  
- Identify performance bottlenecks  
- Analyze failure behavior  
- Visualize system performance using Grafana  

---

# 3. Tools Used

- **k6** → Load and stress testing tool  
- **Grafana** → Data visualization  
- **InfluxDB** → Metrics storage  
- **Docker** → Containerized environment setup  
- **httpbin.org** → Public API for testing  

---

# 4. System Flow

The testing environment works in this flow:

```
k6 (generate load)
   ↓
httpbin API (process requests)
   ↓
InfluxDB (store metrics)
   ↓
Grafana (visualize results)
```

---

# 5. Test Scenarios

## 🟢 5.1 Baseline Throughput Test

- Endpoint: `/get`  
- Virtual Users: 30  
- Duration: 1 minute  

This test represents normal API usage and is used as a performance baseline.

---

## 🟠 5.2 Latency Stress Test

- Endpoint: `/delay/2`  
- Users: 0 → 60 VUs  
- Duration: 2 minutes  

This test simulates network delay and increasing traffic to observe performance degradation.

---

## 🔴 5.3 Failure Behavior Test

- Endpoint: `/status/500`  
- Virtual Users: 25  
- Duration: 1 minute  

This test checks how the system behaves when server errors occur.

---

# 6. How to Run the Test

Run the following command in PowerShell:

```bash
$env:K6_OUT="influxdb=http://localhost:8086/k6"
k6 run script.js
```

All test scenarios are already defined inside `script.js`.

---

# 7. k6 Script Reference

📄 File: `script.js`

The script contains 3 scenarios:
- Baseline Throughput Test  
- Latency Stress Test  
- Failure Behavior Test  

Each scenario simulates different types of real-world traffic conditions.

---

# 8. Results Summary

| Test | Observation |
|------|-------------|
| 🟢 Baseline Test | Stable response, no failures |
| 🟠 Latency Test | Higher response time under load |
| 🔴 Failure Test | Correct HTTP 500 handling |

---

# 9. Key Findings

From the testing results, the following observations were made:

- The API is stable under normal conditions  
- No request failures occurred during all tests  
- Response time increases when load increases  
- Some requests are slower than others (tail latency effect)  
- The system handles concurrency well up to 60 users  

---

# 10. Issues Observed

Although the system performs well, a few issues were identified:

- Inconsistent response times under stress  
- Latency spikes during high traffic  
- No clear performance breaking point reached  

---

# 11. Recommendations

To improve performance in real-world deployment:

- Implement caching to reduce response time  
- Use load balancing for high traffic handling  
- Optimize backend processing speed  
- Add rate limiting for traffic spikes  
- Conduct larger-scale stress testing beyond 60 users  

---

# 12. Screenshots

All evidence is stored in the `screenshots/` folder:

- Docker containers running  
- k6 test execution output  
- Grafana dashboard visualization  
- Retest results  

---

# 13. Conclusion

This project demonstrates how an API behaves under different traffic conditions using k6.

The main takeaway is that:
> Even if an API looks stable on average, performance differences become visible under stress.

This highlights the importance of proper performance testing before deploying real systems.

---

# 14. Video Demonstration

👉 https://youtube.com/

---

# 📌 Repository Structure

```
ITT440-Performance-Testing/
│
├── script.js
├── README.md
└── screenshots/
    ├── grafana.png
    ├── k6-result.png
    ├── docker.png
    └── retest.png
```

---

# ⭐ Final Note

This project combines:
- Real API testing
- Load simulation
- Performance monitoring
- Data visualization

All tests were executed using real-time metrics collection with Grafana and InfluxDB.
