**Splunk Firewall Dashboard**

Greetings, everyone! In this repository, I will delve into the intricacies of creating a Firewall dashboard using Splunk.

**Splunk** is a powerful tool designed for log analysis, simplifying tasks such as data collection, management, sorting, and searching. Within the Splunk tool, we employ SPL _(Search Processing Language)_ to navigate and query the data. You can install Splunk from the official website, and a free version is available.

For the Firewall log, I sourced data from a GitHub repository. 

Upon obtaining data, the first crucial step is to determine its structure—whether it is structured or unstructured. In my case, the data is structured, and extensive, and has been divided into two files. Both files have been uploaded to Splunk.

**Getting Data In:**

1. Access Splunk, either through the cloud version or locally with the free or enterprise version
   
   <img width="864" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/299b509f-a18b-4c55-9411-47070904a567">

3. Add data
   
   <img width="638" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/f7e2a3bd-8cdf-4f75-b41e-03c806426a1e">

4. Upload Data
   
 <img width="817" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/18c14148-2154-433c-ba88-47f3e710d04c">

 
5. Select the source type
   <img width="689" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/32fdb501-2da7-4713-b43f-66efb651cced">
   
   <img width="940" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/b64d0af0-0453-483c-ac57-464e3a847c58">
   
6. Update the input setting. I left it to default and proceeded to the next steps.
   
7. Click on Search and Reporting in the Splunk.
   <img width="957" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/84158b58-6c36-4803-ac6b-fce71990dd55">

8. Using SPL language search the desired fields. For instance, sourcetype="your_sourcetype" | table source_ip. sourcetype="your_sourcetype" | table dest_ip, sourcetype="your_sourcetype" | table port. It can searched individually. Also, it can be searched in a single search SPL like sourcetype="your_sourcetype" | table source_ip, dest_ip, port. In this command, we are exploring ourselves in fields, and Statistics. Source type is a way to categorize or label the type of data you're working with.
9. Let's break the above command -- **fields** are the individual pieces of data you can work with, such as "source IP address," "destination IP address," or "timestamp." A **table** is like a structured way of organizing information.
    <img width="953" alt="image" src="https://github.com/srisowmya2000/SplunkFirewalldashboard/assets/59259117/c4aa34b4-ee21-4a7d-8b5b-a34b87bebf43">
10. 

   





