# MOHAMAD AIMAN FAIZ BIN MAZLAN

---

# Performance Evaluation of HTTP Response Behavior Under Concurrent Load Using K6 on a Public API Service

## Student Information

| Item | Details |
|------|---------|
| **Name** | MOHAMAD AIMAN FAIZ BIN MAZLAN |
| **Student No.** | 2024369211 |
| **Course** | ITT440 – Network Programming |
| **Assignment** | Individual Assignment (10%) |

---

# 1. Project Overview

This project evaluates HTTP response behavior under concurrent load using **k6** on a public API service.

Target API:

https://httpbin.org/

The system is tested under different network conditions to simulate real-world API behavior such as normal traffic, latency, and failure responses.

Performance results are monitored using **InfluxDB** and visualized using **Grafana**.

---

# 2. Problem Statement

Modern APIs must handle concurrent users efficiently. When traffic increases, systems may experience:

- Increased response time
- Reduced throughput
- Higher error rates

This project analyzes these behaviors using structured performance testing.

---

# 3. Objectives

- Evaluate HTTP response under concurrent load  
- Measure response time and throughput  
- Identify system bottlenecks  
- Analyze failure behavior  
- Visualize metrics using Grafana  

---

# 4. Tools Used

- k6 (Performance Testing)
- Grafana (Visualization)
- InfluxDB (Metrics Storage)
- Docker (Container Environment)
- httpbin.org (Test API)

---

# 5. Test Scenarios

## 5.1 Baseline Throughput Test

**Endpoint:** `/get`  
**Users:** 30 VUs  
**Duration:** 1 minute  

### Purpose:
- Measure normal API performance  
- Establish baseline throughput  
- Verify system stability  

---

## 5.2 Latency Stress Test

**Endpoint:** `/delay/2`  
**Users:** 0 → 60 VUs  
**Duration:** 2 minutes  

### Purpose:
- Simulate network delay  
- Observe response time degradation  
- Analyze performance under stress  

---

## 5.3 Failure Behavior Test

**Endpoint:** `/status/500`  
**Users:** 25 VUs  
**Duration:** 1 minute  

### Purpose:
- Simulate server failure  
- Measure error handling capability  
- Observe system stability under errors  

---

# 6. k6 Test Script

```javascript
import http from 'k6/http';
import { check, sleep } from 'k6';

export const options = {
  scenarios: {
    "Baseline Throughput Test": {
      executor: 'constant-vus',
      vus: 30,
      duration: '1m',
      exec: 'baselineTest',
    },

    "Latency Stress Test": {
      executor: 'ramping-vus',
      stages: [
        { duration: '30s', target: 20 },
        { duration: '1m', target: 60 },
        { duration: '30s', target: 0 },
      ],
      exec: 'latencyTest',
    },

    "Failure Behavior Test": {
      executor: 'constant-vus',
      vus: 25,
      duration: '1m',
      exec: 'failureTest',
    },
  },
};

export function baselineTest() {
  const res = http.get('https://httpbin.org/get');

  check(res, {
    'status is 200': (r) => r.status === 200,
  });

  sleep(1);
}

export function latencyTest() {
  const res = http.get('https://httpbin.org/delay/2');

  check(res, {
    'status is 200': (r) => r.status === 200,
  });

  sleep(1);
}

export function failureTest() {
  const res = http.get('https://httpbin.org/status/500');

  check(res, {
    'status is 500': (r) => r.status === 500,
  });

  sleep(1);
}
```

---

# 7. Execution Command

```bash
$env:K6_OUT="influxdb=http://localhost:8086/k6"
k6 run script.js
```

---

# 8. Results Summary

| Test Name | Observation |
|-----------|------------|
| Baseline Throughput Test | Stable response, high throughput |
| Latency Stress Test | Increased response time under load |
| Failure Behavior Test | Correct HTTP 500 error handling |

---

# 9. Conclusion

This project successfully evaluates HTTP response behavior under concurrent load.

Findings:

- System performs well under normal load
- Performance degrades under stress conditions
- Error handling works as expected

Grafana provides clear visualization of system behavior.

---

# 10. Video Demonstration

YouTube link:
https://youtube.com/
