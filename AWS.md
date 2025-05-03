AWS stands for ( Amazon web services ) is a company that delivers online computing services over the internet ( Cloud ). Computing services like Storage , servers , software’s , database , analytics and intelligence etc . There are many services like EC2, ELB , VPC , S3 bucket etc .
Cloud Computing: It simply follow the client server model . 

1. Client make the request to the server and server fulfil if its valid request . 

There are 3 type of Deployment model for cloud .

1. **Public cloud** : Easily accessible publicly . for example - you can build a new software or move the existing one . you can access this network for any where .
2. **On-premises** - Also known as private cloud . You cannot access this category from anywhere . For this you have to be in specific network in order to access this cloud model 
3. **Hybrid** - As name suggest Hybrid combination of both private and public . for example you are  working on an application that are hosted in cloud but you can only access on premises infrastructure . 

**benefits of cloud computing .** 

1. Cost saving
2. flexible
3. scalable 
4. secure
5. on-demand resource
6. more focus on business

**AWS is a virtual server . AWS EC2  stand for elastic cloud computing .**

You can run multiple virtual machine in single computer , but when you run on cloud environment they are known as **[** I**nstances ]** . 

 **** 

Instance type in AWS .

1. **General Purpose Instance** : It fit in many purpose like 
    1.  Application servers
    2. Gaming servers
    3. Backends servers for companies
    4. Small and medium databases 
    
    1. **Compute Optimized Instances** : These are best when you need high compute services . This type is also best for above services . high - performance and compute- intensive needs
    
    1. **Memory Optimized Instance :** This type can deliver large datasets workloads fast . The Memory Optimized Instances are best when huge amount of data need to be preloaded before running the app
    
    1. **Accelerated Computing Instance** : This type use Hardware accelerators . The accelerated  computing instances are best for graphics application and streaming
    
    1. **Storage Optimized Instances :** This type is best when you have datasets on local storage . some examples are -
        1.  Large file systems
        2. Data Warehouses
        3. Online transaction systems 
        
        The storage Optimized Instances are designed to deliver many inputs as fast as possible . 
        

## AWS EC2 Scaling

 Scaling is about added more resources according to your need and release them when they are no longer needed . makes scale of up and down easily .

***note : make sure you have the scalable architecture that handles change in demand .**

**AWS EC2 Auto Scaling**

Aws auto scaling services allows you to add or remove EC2 instance automatically . It automate the capacity to the demand . 

There are two approaches : 

1. Dynamics scaling : respond to changing in demand
2. Predictive scaling : Schedules the number of instance based on a predicted demand . Dynamic and Predictive scaling can be combined to scale faster . 

The auto scaling groups allows you to have dynamic environment . you can set minimum capacity , the desired number , and the maximum capacity .

## AWS Elastic load balancing

Load balancer is use to distribute the network traffics ( Load ) among the resources . So that no other resources get overload with traffics  . 

The load balancer is single point of contact for incoming web traffics . The balancer accepts the valid request and send them to appropriate instances 

## AWS Cloud Messaging and Queuing

Monolithic and Microservices

Applications is made up multiple component . These components are communicate with each other . A communication can request data , fulfil request and keep the application running . 

**MONOLITHIC APPLICATION** : An architecture with a tightly coupled component is known as monolithic application

monolithic application can be vulnerable when one component fails . 

In worst case , This can cause an whole services to go down . 

**MICROSERVICES APPLICATION :** These system are loose coupled, means it maintain the services if one component fail . 

AWS has two services that make this integration :- 

1. AWS Simple Notification Services ( **AWS SNS** ) . 
2. AWS Simple Queue services ( **AWS SQS** ).

 ****

### **Amazon SNS (Simple Notification Service):**

**Imagine a Newspaper Stand:**

- **Publishers (senders):** These are like people or systems that want to share news. They drop off their news at the newspaper stand.
- **Topics (channels):** Think of these as different sections in the newspaper stand, like "Sports," "Politics," or "Weather." Each topic represents a category of news.
- **Subscribers (receivers):** People interested in specific news sections. Each subscriber chooses the topics they want to be notified about.

**Example:**

1. A sports fan (subscriber) chooses to receive updates from the "Sports" topic.
2. When a sports article (message) is published, it goes to the "Sports" topic, and the sports fan gets notified about the latest sports news.

### **Amazon SQS (Simple Queue Service):**

**Imagine a To-Do List:**

- **Sender (producer):** This is like someone assigning tasks or putting items on a to-do list.
- **Queue (to-do list):** Think of this as a list of tasks. Each task represents a message that needs to be processed.
- **Receiver (consumer):** Someone who takes tasks from the to-do list and completes them.

**Example:**

1. Your friend (sender) puts tasks on a to-do list (queue), like "Buy groceries," "Walk the dog," etc.
2. You (receiver) pick up tasks from the list (queue) and complete them one by one.

### **How SNS and SQS Work Together:**

**Imagine a Bulletin Board at Work:**

- **Bulletin Board (SNS Topic):** A central place where announcements are posted.
- **Colleagues (SQS Queues):** Each colleague has their own to-do list for tasks related to their work.

**Example:**

1. Your boss (publisher) posts an important announcement (message) on the bulletin board (SNS topic).
2. Each department (SQS queue) has its own to-do list. The announcement is added to each department's to-do list.
3. Employees (subscribers) in each department pick up tasks from their to-do list and take appropriate actions.

In this way, SNS is like a bulletin board for broadcasting messages, and SQS is like a to-do list for managing tasks. Together, they allow for efficient communication and task management in a distributed system.

## AWS Serverless Computing

So Serverless is a service in which you don’t have to think about servers . you just have to think about the coding part . it is manage by cloud provider .

**Difference between EC2 and Serverless** : In EC2 you have virtual server to run , to manager but in serverless computing you don’t have think about it just focus on code rest is manage by cloud

**AWS has serverless service called AWS Lambda .**

AWS Lambda is a serverless computing service provided by Amazon Web Services (AWS) that allows you to run code without provisioning or managing servers. In simpler terms, it enables you to execute your code in response to events without worrying about the underlying infrastructure.

Here's a breakdown of how AWS Lambda works:

1. **Function Creation:**
    - You write your code in a supported programming language, such as Python, Node.js, Java, or others.
    - This code is packaged into a deployment package, which includes your code and any dependencies it may have.
2. **Deployment:**
    - You upload your deployment package to AWS Lambda.
    - AWS Lambda automatically takes care of allocating resources (CPU, memory, etc.) for your function.
3. **Trigger:**
    - Your function is not running all the time; it's triggered by specific events, such as changes to data in an Amazon S3 bucket, updates to a DynamoDB table, or HTTP requests through an API Gateway.
4. **Execution:**
    - When an event that triggers your function occurs, AWS Lambda runs your code.
    - It spins up the necessary infrastructure to execute your function, and once the execution is complete, it scales down to zero, meaning you're not paying for idle resources.
5. **Scaling:**
    - AWS Lambda automatically scales your function based on the rate of incoming events. If many events occur simultaneously, AWS Lambda can run multiple instances of your function in parallel to handle the load.
6. **Logging and Monitoring:**
    - AWS Lambda provides logging and monitoring features, allowing you to track the performance and troubleshoot issues.

Here's a simple example using AWS Lambda:

Let's say you have a function written in Python that takes an image uploaded to an S3 bucket, processes it to create a thumbnail, and stores the thumbnail back in another S3 bucket.

1. **Function Code (Python):**
    
    ```python
    import boto3
    
    def lambda_handler(event, context):
        # Retrieve the S3 bucket and key from the event
        source_bucket = event['Records'][0]['s3']['bucket']['name']
        source_key = event['Records'][0]['s3']['object']['key']
    
        # Process the image (create a thumbnail)
        # ...
    
        # Upload the thumbnail to another S3 bucket
        destination_bucket = 'your-thumbnail-bucket'
        # ...
    
        # Return a response (optional)
        return {
            'statusCode': 200,
            'body': 'Thumbnail created successfully!'
        }
    
    ```
    
2. **Trigger:**
    - Set up an S3 bucket to trigger the Lambda function whenever a new image is uploaded.
3. **Execution:**
    - When you upload an image to the specified S3 bucket, AWS Lambda automatically triggers the function, processes the image, and stores the thumbnail in the designated bucket.

This is a basic example, but it illustrates how AWS Lambda allows you to execute code in response to events without managing servers.

**Throttling**: If the demand exceeds the concurrency limits and Lambda is unable to scale up quickly enough to handle the load, it may start throttling requests. Throttling means that some requests will be rejected until there is capacity available to handle them.

**Provisioned Concurrency**: For workloads with more predictable traffic patterns or if you want to ensure low-latency for the first few requests, you can use provisioned concurrency. With provisioned concurrency, you specify the number of pre-warmed instances of your function, and AWS Lambda keeps them ready to handle requests. This helps in avoiding the cold start latency and ensures a faster response time.

**Limitations of Serverless Computing:**

1. **Cold Start Latency:**
    - When a serverless function is invoked after a period of inactivity, there may be a delay known as a "cold start" as the environment is initialized. This can impact the response time for the first request.
2. **Execution Time Limits:**
    - Serverless functions have execution time limits imposed by the platform (e.g., AWS Lambda has a default limit of 15 minutes). Long-running tasks may need to be divided or handled differently.
3. **Limited Execution Environment:**
    - Serverless platforms may have restrictions on the runtime environment and available resources, limiting the types of applications that can be deployed.
4. **Stateless Nature:**
    - Serverless functions are designed to be stateless, which can complicate certain types of applications that require maintaining state between requests. Persistent storage solutions are often required.
5. **Debugging Challenges:**
    - Debugging and monitoring serverless functions can be more challenging compared to traditional server-based applications. Tools and techniques may differ, and logs may be distributed across multiple instances.
6. **Vendor Lock-In:**
    - Adopting a serverless platform may result in vendor lock-in. If your application becomes heavily dependent on the specific features and offerings of a particular provider, it could be challenging to migrate to another platform.
7. **Cost Uncertainty:**
    - While serverless is often cost-efficient, predicting costs can be challenging, especially in highly dynamic or rapidly changing workloads. Unanticipated usage patterns can lead to unexpected costs.
