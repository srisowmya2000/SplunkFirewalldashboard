**Splunk Firewall Dashboard**

Greetings, everyone! In this repository, I will delve into the intricacies of creating a Firewall dashboard using Splunk.

**Splunk** is a powerful tool designed for log analysis, simplifying tasks such as data collection, management, sorting, and searching. Within the Splunk tool, we employ SPL _(Search Processing Language)_ to navigate and query the data. You can install Splunk from the official website, and a free version is available.

For the Firewall log, I sourced data from a GitHub repository. 

Upon obtaining data, the first crucial step is to determine its structure—whether it is structured or unstructured. In my case, the data is structured, and extensive, and has been divided into two files. Both files have been uploaded to Splunk.

**Getting Data In:**

1. Access Splunk, either through the cloud version or locally with the free or enterprise version
   
2. Add data.
   <img width="458" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/f02b6709-cacf-4e70-84af-f2c2e3fbebea">


3. Upload Data
   
 <img width="817" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/18c14148-2154-433c-ba88-47f3e710d04c">

 
4. Select the source type
   <img width="689" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/32fdb501-2da7-4713-b43f-66efb651cced">
   
   <img width="940" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/b64d0af0-0453-483c-ac57-464e3a847c58">
   
6. Update the input setting. I left it to default and proceeded to the next steps.
   
7. Click on Search and Reporting in the Splunk.
   <img width="957" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/84158b58-6c36-4803-ac6b-fce71990dd55">

8. Using SPL language search the desired fields. For instance, sourcetype="your_sourcetype" | table source_ip. sourcetype="your_sourcetype" | table dest_ip, sourcetype="your_sourcetype" | table port. It can searched individually. Also, it can be searched in a single search SPL like sourcetype="your_sourcetype" | table source_ip, dest_ip, port. In this command, we are exploring ourselves in fields, and Statistics. Source type is a way to categorize or label the type of data you're working with.
9. Let's break the above command -- **fields** are the individual pieces of data you can work with, such as "source IP address," "destination IP address," or "timestamp." A **table** is like a structured way of organizing information.
    <img width="953" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/c4aa34b4-ee21-4a7d-8b5b-a34b87bebf43">
10. We can sort the search results by adjusting the time. Lik from All time to 24 hours.
11. Other than the table there are other commands like chart, and stats time chart, which can be used to give the statistics table and also will give the visualization. For instance, index="your_index" sourcetype="your_sourcetype" | chart count over field name
    <img width="947" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/57aa9ac8-869e-47e5-bf8d-ddba7bcfb531">

12. Also we can use a time chart or stats. [2] Attaching the SPLUNK commands list
13. Jumping into visualization. There are many graphs in Splunk like bar graphs, line charts, pie charts, heat maps, etc.
14. Now by using the above command we have generated a Pie chart - sourcetype="your_sourcetype" | chart count over field name
    <img width="931" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/33b5856c-320e-4420-840c-68029a4ce486">

15. Similarly, we can generate different types of graphs. We need to understand clauses like "by", and "over" The by clause is used to group events based on one or more fields. The over clause is used with the time chart command to specify a field for which the time-based chart is created. [3]

16. Dashboards:
    Dashboards are views that are made up of panels. The panels can contain modules such as search boxes, fields, charts, tables, and lists. Dashboard panels are usually connected to reports.[4]

17. Types of dashboard: Classic Dashboard and Dashboard Studio. In Dashboard Studio there are other two types Absolute and Grid. [5] About creating the dashboard attached is the SPLUNK documentation about creating a dashboard. In this Repo, we will stick to the dashboard studio Grid. Name the dashboard and select the grid type. 

<img width="954" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/ad24ece7-a3bf-4c2e-900d-7e5ce41091de">

18. Select on the Database Symbol
 <img width="932" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/61b44efc-78f3-4cfa-84e3-f43c4d3b83d2">

 19. In the data Overview section we have to create a search with SPL.
      <img width="265" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/b907f6ab-ea49-478a-acf1-53b39c430eaf">

20. Click on Add chart after your search and insert your desired graphs.
    <img width="119" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/49328c35-f036-4395-90ba-288253b77620">


21. Now after adding search and chart
    <img width="951" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/1e2f6d62-1cfd-4b62-b86a-308087dd8ec9">

21. Now keep adding your searches related to IP address, Ports, Status codes, HTTPS, display device name, and device IDs. There are many things we can do.
22. The final dashboard that I have developed looks like this. 

![Firewall logs](https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/aab979ce-3b8b-409f-b444-f00e52965bac)
































































References: 
[2]https://www.splunk.com/en_us/blog/tips-and-tricks/search-commands-stats-chart-and-timechart.html 
[3] https://docs.splunk.com/Documentation/SCS/current/SearchReference/Introduction
[4] https://docs.splunk.com/Documentation/Splunk/9.1.1/SearchTutorial/Aboutdashboards#:~:text=Dashboards%20are%20views%20that%20are,a%20new%20or%20existing%20dashboard. 
[5]https://docs.splunk.com/Documentation/Splunk/9.1.1/SearchTutorial/Createnewdashboard 
    

   





