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
 <img width="752" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/3b5f0534-18f1-4237-91a8-2210188abea9">
 
4. Select the source type. Set the source type. 
  <img width="935" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/5f960382-541b-448c-9678-a26d1ef085db">

5. Update the input setting. I left it to default and proceeded to the next steps.
   
6. Click on Search and Reporting in the Splunk.
   <img width="950" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/060f85bd-0953-4a13-b033-b06d39a83b5b">

7. Using SPL language search the desired fields. For instance, sourcetype="your_sourcetype" | table source_ip. sourcetype="your_sourcetype" | table dest_ip, sourcetype="your_sourcetype" | table port. It can searched individually. Also, it can be searched in a single search SPL like sourcetype="your_sourcetype" | table source_ip, dest_ip, port. In this command, we are exploring ourselves in fields, and Statistics. Source type is a way to categorize or label the type of data you're working with.
9. Let's break the above command -- **fields** are the individual pieces of data you can work with, such as "source IP address," "destination IP address," or "timestamp." A **table** is like a structured way of organizing information.
   
10. We can sort the search results by adjusting the time. Lik from All time to 24 hours.
11. Other than the table there are other commands like chart, and stats time chart, which can be used to give the statistics table and also will give the visualization. For instance, index="your_index" sourcetype="your_sourcetype" | chart count over field name
   <img width="956" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/62aac0ac-3db5-4aed-b9dc-55863e86a1c3">

12. Also we can use a time chart or stats. [2] Attaching the SPLUNK commands list
13. Jumping into visualization. There are many graphs in Splunk like bar graphs, line charts, pie charts, heat maps, etc.
14. Now by using the above command we have generated a Pie chart - sourcetype="your_sourcetype" | chart count over field name
   <img width="935" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/0b85fe2e-e538-47f2-8747-120015b8910a">

15. Similarly, we can generate different types of graphs. We need to understand clauses like "by", and "over" The by clause is used to group events based on one or more fields. The over clause is used with the time chart command to specify a field for which the time-based chart is created. [3]

16. Dashboards:
    Dashboards are views that are made up of panels. The panels can contain modules such as search boxes, fields, charts, tables, and lists. Dashboard panels are usually connected to reports.[4]

17. Types of dashboard: Classic Dashboard and Dashboard Studio. In Dashboard Studio there are other two types Absolute and Grid. [5] About creating the dashboard attached is the SPLUNK documentation about creating a dashboard. In this Repo, we will stick to the dashboard studio Grid. Name the dashboard and select the grid type. 


18. Select on the Database Symbol

 <img width="690" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/33d7b2eb-123a-4fd0-98e6-c46e70621f31">


 19. In the data Overview section we have to create a search with SPL.
     <img width="263" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/f35b65ee-c6ee-49f6-8f39-393af7044631">
 
21. Click on Add chart after your search and insert your desired graphs.
    <img width="115" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/1dfa7579-a885-464b-9691-de35e1933e84">


22. Now after adding search and chart
    <img width="961" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/6c7ec6b7-1125-4843-bdc0-1f06a1073353">


21. Now keep adding your searches related to IP address, Ports, Status codes, HTTPS, display device name, and device IDs. There are many things we can do.
22. The final dashboard that I have developed looks like this. 

![Firewall logs](https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/8cd6fe8a-c52b-4fad-8ca4-a0ef983c48d8)

































































References: 
[2]https://www.splunk.com/en_us/blog/tips-and-tricks/search-commands-stats-chart-and-timechart.html 
[3] https://docs.splunk.com/Documentation/SCS/current/SearchReference/Introduction
[4] https://docs.splunk.com/Documentation/Splunk/9.1.1/SearchTutorial/Aboutdashboards#:~:text=Dashboards%20are%20views%20that%20are,a%20new%20or%20existing%20dashboard. 
[5]https://docs.splunk.com/Documentation/Splunk/9.1.1/SearchTutorial/Createnewdashboard 
    

   





