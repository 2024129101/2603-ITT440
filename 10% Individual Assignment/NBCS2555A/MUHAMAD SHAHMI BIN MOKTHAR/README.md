# Performance Testing and Bottleneck Analysis of DummyJSON Products API Using Apache JMeter

Course: ITT440 - Network Programming \
Group: NBCS2555A \
Name: Muhamad Shahmi Bin Mokthar \
Matrix No.: 2024727655

---
## Project Overview
This project evaluates the performance and scalability of the DummyJSON Products API using Apache JMeter.

The project focuses on analyzing API behavior under different concurrent user loads using Load Testing, Stress Testing, and Spike Testing techniques.

---

## Tool Used

- Apache JMeter 5.6
- Java JDK
- Windows 11

---

## Target API

REST Countries API \
https://dummyjson.com/products

---

## Objectives

- Evaluate API performance under different workloads
- Analyze response time and throughput
- Identify bottlenecks during high traffic
- Observe API behavior during sudden traffic spikes

---

## Test Types

### 1. Load Test
Purpose:
Evaluate API performance under normal traffic conditions.

| Setting | Value |
|---|---|
| Users | 50 |
| Ramp-up | 30 seconds |
| Duration | 5 minutes |

<p align="center">
  <img src="Screenshots/Load%20Test%20Config.png" alt="Load Test Config" width="800">
</p>

---

### 2. Stress Test
Purpose:
Determine system behavior under excessive load.

| Setting | Value |
|---|---|
| Users | 150 |
| Ramp-up | 60 seconds |
| Duration | 5 minutes |

<p align="center">
  <img src="Screenshots/Stress%20Test%20Config.png" alt="Stress Test Config" width="800">
</p>

---

### 3. Spike Test
Purpose:
Analyze API response during sudden traffic spikes.

| Setting | Value |
|---|---|
| Initial Users | 20 |
| Spike Users | 150 |
| Spike Time | 5 seconds |
| Duration | 3 minutes |

<p align="center">
  <img src="Screenshots/Spike%20Test%20Config.png" alt="Spike Test Config" width="800">
</p>

---

## HTTP Request Configuration

| Field | Value |
|---|---|
| Protocol | https |
| Server Name | dummyjson.com |
| Method | GET |
| Path | /products |

<p align="center">
  <img src="Screenshots/http%20request%20config.png" alt="HTTP Request Config" width="800">
</p>

---

## Key Performance Indicators (KPIs)

- Average Response Time
- Throughput
- Error Rate
- Latency
- 95th Percentile Response Time

---

## Project Structure

```plaintext
MUHAMAD SHAHMI BIN MOKTHAR\
│
├── README.md
├── screenshots/
├── jmeter/
└── Performance Testing and Bottleneck Analysis of DummyJSON Products API Using Apache JMeter.pdf
```

## Aggregate Report Results

| Test Type | Samples | Average (ms) | Maximum (ms) | Error Rate | Throughput |
|---------|---------|---------|---------|---------|---------|
| Load Test | 72,076 | 197 | 3,112 | 0.00% | 240.1 req/sec |
| Stress Test | 74,744 | 542 | 16,186 | 0.00% | 248.4 req/sec |
| Spike Test | 46,915 | 568 | 2,343 | 0.00% | 259.9 req/sec |

## Result

- Load Test
<p align="center">
  <img src="Screenshots/Load%20Test%20Aggregate%20Report.png" alt="Load Test Aggregate Report" width="800">
</p>

- Stress Test
<p align="center">
  <img src="Screenshots/Stress%20Test%20Aggregate%20Report.png" alt="Load Test Aggregate Report" width="800">
</p>

- Spike Test
<p align="center">
  <img src="Screenshots/Spike%20Test%20Aggregate%20Report.png" alt="Load Test Aggregate Report" width="800">
</p>

- Average Response Time (ms)
<p align="center">
  <img src="Screenshots/Average%20response%20time%20comparison.png" alt="Average Response Time Comparison" width="600">
</p>
<p align="center">
The graph shows that response time increased significantly during Stress Test and Spike Test due to 
higher concurrent traffic.
</p>

- Throughput Comparison
<p align="center">
  <img src="Screenshots/Throughput%20Comparison.png" alt="Throughput Comparison" width="600">
</p>
<p align="center">
The throughput graph shows that the API handled more requests per second during higher traffic 
conditions. 
</p>

## Key Findings

- Zero request failures across all testing scenarios.
- Response time increased as workload increased.
- The API remained stable under concurrent traffic.
- Throughput remained consistently high.
- The API demonstrated strong scalability and reliability.

---

## Recommendations

- Implement caching mechanisms
- Use CDN services
- Optimize API response handling
- Apply load balancing strategies
- Continuously monitor API performance.

---

## Conclusion

The DummyJSON Products API maintained a 0.00% error rate across all testing scenarios while handling large volumes of concurrent requests.

The results demonstrate excellent reliability, stability, and scalability when tested using Apache JMeter.

---

## YouTube Video Link

<insert-link>

---
