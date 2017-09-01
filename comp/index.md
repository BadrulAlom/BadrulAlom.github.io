---
layout: default
---

## Computing Fundamentals
Computing for Data Science covers a wide range of areas. 

### Programming
Python, R, and Scala are three widely used programming languages in data science.
R is widely used for statistical analysis (increasingly overtaking SAS)
Python is widely used as a general purpose programming language plus machine learning (increasingly overtaking Matlab)
Scala is the preferred language for using Apache Spark. Spark can work well with other languages, most notable python, but Scala is similar to Java and therefore ensures better performance
Then there is Julia, a language that claims to combine the benfits strngth of R and Python for ease of use and statistical capability, with Java for performance, meaning that you can prototype and implement in the same language. It's relatively new but gaining traction.

- [Python Tips](https://github.com/BadrulAlom/Data-Science-Notes/tree/master/comp/Python.ipynb)

My view: I'm going with Python and Scala. Python is used widely in machine learning though frustratingly it is single-threaded (can't make use of multiple CPU cores), while scala is the language to learn for big data

### Cloud computing
Cloud computing is becoming increasingly popular. It's the idea of moving from having IT systmes maintained in-house by ones own IT department, to having it managed by external providers such as Amazon and Microsoft, and interacting with it through the web on a pay as you go basis. The ability to do this opens up new business models such as:
- Infrastructure As A Service - whereby computer hardware is available on demand and you can choose what you do with it
- Platform As A Service - whereby computer hardware + operating system are available on demand and you can choose what you do with it
- Software As A Service - where by hardware + Operating system + user software is available on demand and you can just interact with it without needing it install anything

In the cloud computing space the three main providers are [Amazon Web Services](https://aws.amazon.com/), [Microsoft Azure](https://azure.microsoft.com), and [Google Cloud Compute](https://cloud.google.com/compute/), with the first two currently being the dominant players.

My view: Not much to choose between them really. The core functionality is about the same, with AWS and Azure a little more advanced. Then they all have additional bells and whistles (e.g. APIs that perform machine learning) that would tie you in to their platform. But I find them all to be an expensive option for heavy duty machine learning and general experimentation vs. having your own custom desktop. Would say use cloud for day to day running where you can optimize for lowest possible cost over the long-term rather than R&D.

### Databases
For years relational SQL databases were the dominant force in the database space with Oracle and SQL Server being two of the most established enterprise products.
However in recent years NOSQL (Not-Only-SQL) databases have taken a hold as being better suited for storing unstructured data.

My view: I'm generally a fan of SQL Server and like the R and Python extensions they've built in. However I haven't yet played around with NoSQL databases and keen to try them out, particularly graph databases like Neo4j.

### Linux

My view: A lot of data science is done on the Linux platform. I will say I'm not a fan of Linux however it has increasingly become my main operating system and I've grown to make peace with it. Is now my primary OS (Ubuntu 16.04). 

- [Linux Tips](comp/linux)

### Key Readings

- [Data Engineering at Slack](https://slack.engineering/data-wrangling-at-slack-f2e0ff633b69#.qssvyfzdp)

