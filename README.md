<h1>Linux Log File Analysis, Automation & SIEM Visualization</h1>


<h2>Description</h2>
This project showcases my ability to analyze Linux authentication logs, detect suspicious activity, automate log parsing with Python, and visualize attack patterns using Splunk.
Throughout the lab, I identified brute-force attempts, abnormal session behavior, and repeated authentication failures — then validated those findings using automation and SIEM dashboards.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Splunk</b> 
- <b>Python</b>
- <b>Visual Studio Code</b>
- <b>Excel / Google Sheets</b>

<h2>Program walk-through:</h2>

<p align="center">
I began by manually reviewing a Linux authentication log (<i>Linux_2k.log</i>) to identify potential brute-force activity and unauthorized access attempts.
I focused on the first 20–40 lines and documented notable entries such as invalid users, repeated failed logins, and suspicious IP addresses.
<br/><br/>
<img width="2039" height="1188" alt="image" src="https://github.com/user-attachments/assets/bf4980cf-28be-48be-950e-7b9e631778df" />

<br />
<br />
<b>Identifying Suspicious Events:</b><br/>
I flagged repeated failed logins, attempts targeting the root account, and abnormal session openings/closings.
These patterns strongly suggested automated brute-force activity.
<img width="2039" height="1188" alt="image" src="https://github.com/user-attachments/assets/a3dc79e2-5d9f-437c-b1ee-1260086eb7ec" />

<br/><br/>
<br />
<br />
<b>Organizing Events in Excel:</b><br/>
Suspicious entries were exported into a CSV file and organized in Excel/Google Sheets to identify patterns such as repeated attempts from the same IP.
<img width="2700" height="1109" alt="image" src="https://github.com/user-attachments/assets/cb6d828a-d8d3-4293-9cd7-d849b75e980f" />

<br/><br/>
<br />
<br />
<b>Python Automation:</b><br/>
I wrote a Python script (<i>log_analysis.py</i>) to automatically scan the log for keywords like <i>invalid user</i>, <i>user unknown</i>, and <i>authentication failure</i>.
Matching lines were added to a list and exported to CSV for further analysis.
<br/><br/>
<img width="1084" height="672" alt="image" src="https://github.com/user-attachments/assets/081eb501-a445-4178-9fc8-4d94d6f37800" />
<img width="945" height="320" alt="image" src="https://github.com/user-attachments/assets/c9b84ddd-0a1d-4891-bc7b-2ec9b4f665ff" />


<br />
<br />
<b>Splunk SIEM Upload:</b><br/>
I uploaded the log file into Splunk Enterprise using <i>Settings → Add Data</i>.
Splunk automatically detected the source type and indexed the log for searching and visualization.
<br/><br/>
<img width="2558" height="834" alt="image" src="https://github.com/user-attachments/assets/216725fa-0acb-4258-9903-d8f405effda9" />

<br />
<br />
<b>Searching for Suspicious Activity:</b><br/>
Using Splunk’s search bar, I filtered for failed authentication attempts using the query:source="Linux_2k.log" host="Random" sourcetype="Linux_2k.log"("Failed
password" OR "authentication failure" OR "invalid user" OR "user unknown")
<img width="2571" height="1253" alt="image" src="https://github.com/user-attachments/assets/f7a89a92-3a65-4d81-8be6-b3e10effc788" />

<br/><br/>
<br/>
<b>Event Pattern Analysis:</b><br/>
Splunk revealed repeated login failures from IP <i>207.243.167.114</i>, often targeting the <i>root</i> account within seconds — a strong indicator of brute-force attempts.
<br/><br/>
<img width="2593" height="1069" alt="image" src="https://github.com/user-attachments/assets/f6937a45-7219-40a2-b242-138c923b89dc" />

<br/><br/>
<br/>
<b>Statistics & Pivot Table:</b><br/>
I used Splunk’s Statistics and Pivot views to group events by username, IP address, and event count.
This helped visualize which accounts and IPs were most frequently targeted.
<br/><br/>
<img width="2902" height="1270" alt="image" src="https://github.com/user-attachments/assets/48cb971f-4eec-4d9f-8749-f0a052b7a7e0" />

<br/><br/>
<b>Attack Timeline Visualization:</b><br/>
A line chart visualization showed sharp spikes in authentication failures over short intervals.
These bursts of activity are typical of automated brute-force attacks.
<br/><br/>
<img width="2943" height="1336" alt="image" src="https://github.com/user-attachments/assets/5aaa014f-bd10-4c29-b2a8-e4abebf74d1a" />

</p>

<h2>Key Takeaways</h2>

- <b>Identified brute-force attempts through manual log review
- <b>Automated suspicious event detection using Python
- <b>Used Splunk SIEM to visualize authentication failure patterns
- <b>Demonstrated real SOC analyst workflows
- <b>Showed ability to interpret logs, detect anomalies, and communicate findings

<h2>What I Learned</h2>

- <b>How attackers attempt brute-force access using repeated login failures</b>
- <b>How to automate log parsing with Python</b>
- <b>How SIEM tools correlate events and reveal attack patterns</b>
- <b>How to visualize authentication failures over time</b>=
- <b>How to document cybersecurity investigations professionally</b>

