# Introduction to Maltego

- Maltego is  an open-source intelligence (OSINT) and graphical link analysis  tool used for gathering and analyzing information from the internet.
- It helps find connections between different things like websites, emails, IP addresses, social media profiles, and more.
-  By visualizing these connections in a graph, it makes it easier to see hidden relationships, which is useful for tasks like cybersecurity investigations, fraud detection, and penetration testing.

-------
## Getting Started with Maltego

***Before using Maltego, you need to create an account and sign in:***
-  Launch Maltego on Kali Linux , you can search for Maltego in the application menu and launch it directly or type maltego command in terminal and run
![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots/maltego_opening.png)
- After launching Maltego, you'll be prompted to log in using your Maltego account credentials. If you haven’t created an account yet, follow the registration process on the [Maltego website](https://www.maltego.com/) to sign up.
- Once logged in, you can start exploring the tool’s features for open-source intelligence (OSINT), mapping relationships, and analyzing various entities (such as IPs, domains, people, etc.) on the web
![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots/maltego_interface.png)
- You can  create a new graph or open a graph you already saved
![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots/new_graph.png)

------------

 ##  How Maltego Works:
- Start by dragging and dropping a domain (or email, IP address, etc.) into Maltego’s workspace.
![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots/new_graph.png)
-  After placing the domain, run "transforms" to gather related information. This could include DNS records, WHOIS data, email addresses, IP address, location and more.
![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots/run_transforms.png)
-  Maltego will create a graph showing all the related entities and how they are connected.
-  You can continue running transforms on new entities to uncover more relationships

 - Once the graph is complete, we can export it
![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots/maltego_toolbar_options.png)
 This image shows the export and report generation options available in Maltego. The top menu includes features such as:
- Generate Report – Create a detailed report of the analysis.
- Export Graph to Table – Convert the graph into a structured table format.
- Export Graph as Image – Save the visualized graph as a PNG or other image formats.
- Export Graph as XML – Save the graph data in XML format for further processing.

  
