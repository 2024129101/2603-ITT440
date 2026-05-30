<div align="justify">
# AIMAN HAKIM BIN BADRUL ZAMAN

## 1.0 - INTRODUCTION 

Target API : https://fakestoreapi.com

Tool: Apache JMeter 5.6.3 - CMD

Tester : AIMAN HAKIM BIN BADRUL ZAMAN (SID : 2024130077)

<br>
<br>

## 2.0 -  Why Apache JMeter? 
- Jmeter offers a perfect environment for beginners while also providing a large space for skills to grow. It is a low skill floor and high skill ceiling tools. 
- Demonstrating spike, load and soak test easily
- Free to use app and easy to set up as well as run perfectly on Window

<br>
<br>

## 3.0 - Performance Testing Hypothesis

Project Objective:
To evaluate the performance, stability, and scalability of the fakestoreapi.com REST API under various load conditions using Apache JMeter.

### 3.1 Load Test Hypothesis
Hypothesis:
Under a steady load of 300 concurrent users accessing the /products endpoint for 15 minutes, the API is expected to maintain an average response time below 500 ms, a 95th percentile response time below 600 ms, and an error rate of less than 1%, while achieving a throughput of at least 100 requests per second.

### 3.2 Spike Test Hypothesis
Hypothesis:
When subjected to a sudden spike from 50 to 400 concurrent users for 3 minutes (after 5 minutes of normal load), the API is expected to handle the traffic burst without crashing, recover quickly after the spike, maintain an average response time below 800 ms during the spike, and keep the error rate below 2%.

### 3.3 Soak Test (Endurance) Hypothesis
Hypothesis:
Under a sustained load of 150 concurrent users for 2 hours, the API is expected to demonstrate long-term stability with no significant performance degradation (response time increase < 20%), maintain an average response time below 500 ms, and sustain an error rate of 0% throughout the test duration.

### Overall Project Hypothesis
The fakestoreapi.com API is expected to demonstrate good performance, stability, and reliability suitable for a public demo API when tested under moderate load, sudden traffic spikes, and prolonged usage. It is hypothesized that the API will successfully handle the defined load conditions with acceptable response times and minimal to zero errors.

<br>
<br>

## 4.0 - Test Environment Setup and Methodology

### 4.1 Test Environment Setup (visual guide)
For the environment setup, the user can watch the video below.

https://youtu.be/qY2wVylRsRM?si=R5SvOqhR6YLrZSCC 

<br>

### 4.2 Methodology

Apache JMeter operates on GUI. Therefore, no codes are required and just need to fill in the settings for the test template.

#### COMMON SETTINGS
<img width="757" height="362" alt="image" src="https://github.com/user-attachments/assets/d0dcaac3-40a5-4c6a-9ee1-0e4ff1e83b17" />

#### SETTINGS OVERVIEW
<img width="739" height="646" alt="image" src="https://github.com/user-attachments/assets/23caf648-989f-4a0e-b248-3b027ad05a0d" />

<br>
<br>
<br>

## 5.0 Raw Data Presentation

### 5.1 Load Test

#### Performance index
<img width="774" height="200" alt="image" src="https://github.com/user-attachments/assets/b176f04d-e85e-4e91-83c9-a49cb48c608f" />

Performance index points at 0.994 which then can be rated at excellent performance. This index measures user satisfaction and getting 0.994 means that the user is highly satisfied with the API performance.

#### Statistics
<img width="1583" height="225" alt="image" src="https://github.com/user-attachments/assets/1484be9c-372d-4091-9ab4-19f251d2b79e" />

The Load Test with 300 concurrent users achieved an average response time of 248 ms, with 95% of requests completing under 263 ms. The API processed 231.75 transactions per second with a near-perfect error rate of 0.00%

#### Response Time Percentiles
<img width="1503" height="464" alt="image" src="https://github.com/user-attachments/assets/065d7283-bba8-4f86-bfbf-602b9f97fa02" />

#### Response Time Over Time
<img width="1489" height="483" alt="image" src="https://github.com/user-attachments/assets/0bb05625-df07-4ee1-97b2-dd29cf5ff063" />

#### Load Test Overview
fakestoreapi.com excellently handles load test with near-perfect error rate of 0.00%, proving its reliable performance for free public API.

<br>

### 5.2 Soak Test

#### Performance Index
<img width="782" height="192" alt="image" src="https://github.com/user-attachments/assets/d2dd7fa2-5a2a-442c-9741-2bd19d8ec76e" />

An Apdex score of 0.975 is very high. This means users would be highly satisfied with the performance even after running continuously for 2 hours.

#### Statistics
<img width="1579" height="209" alt="image" src="https://github.com/user-attachments/assets/583579fd-37b2-4763-b953-4620b783604a" />

fakestoreapi.com shows a very stable performance with 0 errors throughout 2 hours. The API maintaining a solid average response time of 347 ms and shows a very good endurance for a free public API

#### Response Time Percentile
<img width="1504" height="462" alt="image" src="https://github.com/user-attachments/assets/61b759f3-57ae-41c9-a318-db1deaae3e72" />

#### Response Time Overview
<img width="1468" height="461" alt="image" src="https://github.com/user-attachments/assets/66e181e0-ada5-433e-b30f-3d6a2d8ba2c5" />

#### Soak Test Overview

The Soak Test with 150 concurrent users ran successfully for 2 hours. The API demonstrated excellent stability with 0% error rate and processed 798,152 requests. The average response time remained consistent at 347 ms, and the Apdex score of 0.975 indicates strong user satisfaction even under sustained load.

<br>

### 5.3 Spike Test

#### Performance Index
<img width="760" height="183" alt="image" src="https://github.com/user-attachments/assets/efd14c9f-cb76-4625-9e7e-31ad4e3753c9" />

Apdex score at 0.988 which shows the API excellent performance in taking sudden burst of users

#### Statistics 
<img width="1591" height="205" alt="image" src="https://github.com/user-attachments/assets/031dd1e6-c467-46ae-8416-b857a1df4b85" />

The API handled the Spike Test very well, handling a sudden burst up to 400 users with zero errors, an excellent average response time of 271 ms, and strong throughput of 131 requests per second.

Response Time Percentile
<img width="1469" height="453" alt="image" src="https://github.com/user-attachments/assets/75c797ca-e705-4fe5-b327-9b3ca97a2d8b" />

Response Time Over Time
<img width="1459" height="458" alt="image" src="https://github.com/user-attachments/assets/c545e934-b140-485c-aacf-042d77778c4d" />

#### Spike Test Overview

The Spike Test with a sudden burst of 400 handled well by the API. It shows that the API is reliable and consistent with an average of 270 ms response time, and the Apdex score of 0.988 indicates that the user is very satisfied with the performance.

<br>
<br>

## 6.0 Imporovement Suggestions
This project has successfully established a strong foundation in performance testing using Apache JMeter. The initial tests focused on the /products endpoint provided valuable insights into the API’s behavior under different load conditions. To further enhance the realism and depth of testing, the User is encouraged to expand the test scenarios by incorporating multiple critical endpoints. This includes testing authentication flows such as Login (/auth/login), along with other key operations like viewing single products (/products/{id}), managing carts (/carts), and user-related endpoints.
By simulating complete user journeys (e.g., Login → Browse Products → Add to Cart), the performance tests will better reflect real-world usage patterns, helping to identify bottlenecks across various API functionalities and delivering more comprehensive and actionable results.

<br>
<br>

## 7. 0 Conclusion
The fakestoreapi.com demonstrated strong and reliable performance across all three performance tests. It successfully handled a steady load of 300 users, a sudden spike up to 400 concurrent users, and a prolonged endurance test of 150 users for 2 hours with zero errors (0.00% error rate) in all scenarios.
Response times remained consistently good, with average times ranging between 248 ms to 347 ms, and excellent Apdex scores between 0.975 – 0.988, indicating high user satisfaction. The API showed good stability with no major degradation during long-duration testing and effectively managed sudden traffic bursts.

<br>
<br>

## 8.0 YOUTUBE LINK 
https://youtu.be/qY2wVylRsRM?si=R5SvOqhR6YLrZSCC 

</div>
