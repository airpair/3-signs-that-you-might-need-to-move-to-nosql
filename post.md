####Why NoSQL? 

![Why use NoSQL](https://blog.cloudboost.io/content/images/2015/06/nosql.jpg)

NoSQL databases are a class of databases in which data is NOT stored in tabular relations - Unlike other relational database solutions and this is why it is called "Not Only SQL". Data which is stored in other data-structure other than tabular relations are sometimes better for some scenarios which are outlined later in this post. 

NoSQL databases are great at doing a bunch of things. For example - storing big data for internet scale applications, scenarios which prefer low latency data-storage, improved performance, and more. 

Here are three signs why you should be considering NoSQL databases for your solution: 

#####Your data is BIG: 


You're collecting a ton of data over the internet - like web analytics, sensor data from the Internet of Things (IoT), saving a lot of user data (like tweets in twitter), etc and you need a place to store + have an efficient way to do a "distributed read" on all of the data. If this is what you're looking for - then NoSQL is a perfect fit for you. 

#####You have a "schema less" data:

Data which you're storing in the traditional RDBMS databases like SQL has a pre-defined schema ahead of time. If your schema changes a lot OR if you don’t have a pre-defined schema where you can add a field anytime you like then NoSQL is the good fit for these type of scenarios. 

#####Scale out:

There are two things you can do when you want to scale your solution. You can either scale up where you keep adding more memory, processing capacity and storage to a single machine or you can scale out where you can have multiple machines supporting your solution. 

![Scale up vs Scale out](https://blog.cloudboost.io/content/images/2015/06/KB_Scale_Out-Up.png)

NoSQL is a perfect solution when you have a ton of data that doesn't fit on a single server. Most of the NoSQL databases are horizontally scalable - What I mean by this is you can shard or divide your data into multiple servers and still have efficient access to your data. NoSQL databases are elastic, you can have thousands of nodes / servers and you can scale horizontally well.  

####What you'll be missing? 

#####No relations and joins: 

Most NoSQL databases for example MongoDb has no relation support between tables (Graph Databases like Neo4j does, but that’s a completely different type of database to look at) - Which means there's no support for joins when you query your data. If you have joins between your data you can combine documents together and save them as sub-documents or do a manual join by running two queries over your database.  

#####No atomic operations:

Most of the NoSQL databases like MongoDB have no atomic operations or transactions across multiple tables / record. For example, In MongoDB a single write is atomic but if you write multiple records / documents at the same time then as a whole they're not atomic. If you want to ever need to have transaction support on your data which is critical for your solution. You should store that piece of data in RDBMS instead. 

#####No reporting: 

NoSQL has no reporting in general - as you've used to when you were on RDBMS databases. If you want to generate reports, create graphs, or do something with all of the data in your NoSQL stack, you'll need to start coding and write what we call - ["map-reduce"](https://en.wikipedia.org/wiki/MapReduce) jobs for the reports you want.


####Where is NoSQL the best fit? 

These are few of the sample scenarios where NoSQL is the best fit. Typically these include high-volume / low-latency data-storage scenarios. Few examples of these are:  

#####Storing logs / user analytics data:

![Logs and Analytics](https://blog.cloudboost.io/content/images/2015/06/analytics-600.jpg)

Servers generate a large number of logs that contain useful information about their operation including errors, warnings, and user behaviour. By default, most servers, store these data in plain text log files on their local file systems.

While plain-text logs are accessible and human-readable, they are difficult to use and analyse. NoSQL Column Oriented database like Cassandra is a perfect databases to store log files. Cassandra can handle huge number of writes which is useful when you store logs or Meta data about where user behaviour on your site. 

#####Internet of Things - Storing data from the sensors:

![Internet of things](https://blog.cloudboost.io/content/images/2015/06/IoT-ConnectedDevicesImage.jpg)


Sensor-enabled devices are pumping out a ton of data, but sensor data is only useful if you can do something with it. With NoSQL databases, you can make sense of sensor data, building applications never before possible.

The Internet of Things is a world where all your physical assets and devices are connected to each other and share information, making life easier and more convenient. To enable this inter-connected world, You need to have all the data these devices are pumping out and making sense of it and this is one of the scenarios where NoSQL is the great fit.


####So, do I migrate? 

![SQL vs NoSQL](https://blog.cloudboost.io/content/images/2015/06/RDBMSvsNoSQL.jpeg)

It depends on your application which you're building. If your application has a ton of transactional and relational features - You can go ahead with RDBMS, if your application has a scalability issue with your current data infrastructure. Then I think you seriously need to use NoSQL. You can even use both and this is what most companies do. For piece of data which is related, they tend to go ahead with Relational Database, but for a piece of data which has no relations / or is big data. They use a NoSQL database solution and I think this is the best approach to go forward with. I've written a complete [post](http://blog.cloudboost.io/what-is-polyglot-persistence-and-how-can-it-help-your-app/) about which type of databases to use where. Please feel free to check that out and let me know your thoughts.


