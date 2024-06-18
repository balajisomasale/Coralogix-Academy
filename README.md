# Coralogix-Academy

<details>
  <summary> Introduction to Coralogix </summary>
  Introduction to the Observability World
Introduction to the world of observability
What is observability? 
How is it different than monitoring? What is SaaS Observability and how can it make your life easier? Watch this brief video to find out!

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/c3d65e95-5049-4c14-ae37-ae4d258595fc)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/8f60de34-a5a8-4bc0-8c8e-b409c8d68907)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/b266ca00-35e5-43fd-8d5e-ca4b04f09328)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/9f5517a8-dea1-4361-b9e8-5b92ecd0b5fb)

What Are Logs?

- Logs represent specific events generated by a system.
- Logs almost always contain keys and values, a message field and date and time of event.
- Logs are most easily analyzed when in machine readable format such as JSON.
- Logs using a custom or unstructured format can still be analyzed but require parsing and other data manipulation.
- Most importantly, logs provide real context of why something is happening with messages included to describe issue.

What exactly are metrics? Watch this brief video and learn that:

- Metrics are continuous measurements of a particular aspect of your system over time. This is in contrast to logs with each log being a discrete data point of a specific event, at a specific point in time.
- As metrics are continuous values, they typically are sampled every 30 to 60 seconds to maintain a balance between data volume and data granularity.
- Metrics can be used in calculations such as grouping, adding them up or averaging them. Metrics are also very high performance, meaning you can store and query them for very long periods of time. This gives you long-term historical reporting as well as current operational and numerical insight into what is happening in your system.
- When defining your metrics it’s important to understand cardinality which is the number of unique values for a particular attribute or dimension within a dataset.
- For example, a metric such as an “API request count” can have an attribute like “user IDs” with high cardinality due to the potentially vast number of unique user IDs. On the other hand, an attribute like “response status” which typically includes values like 200, 404, 500, etc., has low cardinality because the number of unique status codes is limited.
- High cardinality can impact storage requirements, cost and query performance so it’s important to be aware of it when designing monitoring systems and dashboards to ensure they remain performant and useful.

What are Traces
What exactly are traces? Watch this brief video and learn that:

- Tracing data shows the detailed, chronological flow of a specific request as it travels and communicates between different components of an application or system. This is in contrast to logs which reflect discrete events generated by different components or services within a system.
- Normal tracing, also known as single-threaded or local tracing, focuses on monitoring the execution of a single thread or process within an application or system.
- Distributed tracing, on the other hand, is designed to track and monitor the flow of operations across multiple interconnected services or components within a distributed system. 
- Traces are typically made up of multiple spans. Each span represents a specific operation or “conversation” within a trace that occurs as part of a request’s journey though an application or distributed system. 
- Traces provide visibility into the duration and latency for each span as well as HTTP statuses where relevant. This empowers you to understand how your system is performing and identify interdependencies and drill into bottlenecks when they occur. 
- Traces also enable you to understand which systems depend on each other, providing for single communication and leaving you with a centralized picture of everything.
- With Coralogix you can correlate your traces with logs and metrics for a fuller view and finally, Coralogix provides its own open-source friendly tracing solution.

</details>

<details>
  <summary>
    Getting Started
  </summary>
Basics of Regions and API Keys:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/fdeb1365-1914-4ead-8ff9-6c61d86910a4)

</details>

<details>
  <summary>
    [Hands-on] Connecting Coralogix to your S3 Archive
  </summary>

An important note is that we need to be the same region: coralogix domain(https://coralogix.com/docs/coralogix-domain/) and aws region

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/c95e18ae-e74d-4d35-9400-902a5e11f86c)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/7e4572fd-36ae-4d62-b18d-bd40c668ef2d)

```
{
    "Version": "2012-10-17",
    "Id": "MyPolicyID",
    "Statement": [
        {
            "Sid": "MyStatementSid",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::739076534691:role/coralogix-archive-us2"
            },
            "Action": [
                "s3:GetObject",
                "s3:ListBucket",
                "s3:PutObject",
                "s3:PutObjectTagging",
                "s3:GetObjectTagging",
                "s3:DeleteObject",
                "s3:DeleteObjectVersion",
                "s3:DeleteObjectTagging",
                "s3:DeleteObjectVersionTagging"
            ],
            "Resource": [
                "arn:aws:s3:::my-coralogix-bucket1",
                "arn:aws:s3:::my-coralogix-bucket1/*"
            ]
        }
    ]
}
```

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/043cbc45-5486-4acd-8490-25311e511dac)

</details>

<details>
  <summary>
    [Hands-on] Coralogix Extensions
  </summary>

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/26bd4240-53e1-4d35-afb5-e16fbb04ced2)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/d8a7efe6-9686-4a2b-bd02-0491e7e52690)

- Once we use `Deploy` option on top right, All Alerts will be created and are visible in `Alert Management`

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/6b9b720d-4a29-405f-8b5d-66e89ee42c0c)

- To remove it, just `remove` from top right where it was deployed. Very fast and effective way in coralogix
  
</details>

<details>
  <summary>
    3.1 Coralogix Academy - OpenTelemetry and Coralogix Integration
  </summary>

  https://coralogix.com/docs/opentelemetry/
</details>


<details>
  <summary>
    [Hands-on] 3.2 Coralogix Academy - OpenTelemetry Lambda Function with Coralogix
  </summary>
Coralogix AWS Lambda Telemetry Exporter: https://coralogix.com/docs/coralogix-aws-lambda-telemetry-exporter/

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/4bced9f6-af65-4b60-85b7-445f022cbb4b)

Create Lambda function again in aws and follow the video for environment variables setup and other 

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/ba0ebb54-a644-4954-ad17-58d1605054cc)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/77fe131b-0bc0-437f-83e2-a9dd4cac7fd6)

Add a layer > choose specific ARN:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/bf65c2f1-e6ce-4aa0-86f5-265c2024e3eb)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/1e87e329-d119-4343-a280-97210b89a5ba)

Back to coralogix:

Logs:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/17b7f1fc-29ff-4211-9bfb-d96195d07414)

Tracing:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/4db3fe82-0eef-490f-a5e1-cafadba392d8)

</details>

<details>
  <summary>
    [3.3 Coralogix Academy - Open Telemetry, Coralogix & Kubernetes
  </summary>
  Kubernetes not connecting in windows 

Before starting, Get to know about Helm ? 

https://circleci.com/blog/what-is-helm/#:~:text=The%20Helm%20application%20library%20uses,commands%20to%20control%20the%20cluster.

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/90ca314b-8449-451d-82fa-da45cf784767)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/846a22f2-9733-416e-b559-102499514eef)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/428d1808-95f8-4a6d-b4d4-a2121014decb)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/533c8de0-457f-406a-a444-49db6f8f4788)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/7e57ec1d-f39b-45b0-8bb5-b23cc2b0ffc2)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/11014aa0-53e4-42aa-9b6f-c2dbe539f36e)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/898fa402-c1d5-4a30-a8a0-5c11837a3200)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/bdad7e55-41ce-44a0-8a83-7c9ba00c327f)

</details>

<details>
  <summary>
   [hands-on] 3.4 Coralogix Academy - ECS to Coralogix using OpenTelemetry
  </summary>
Blog Link: https://coralogix.com/docs/opentelemetry-using-ecs-ec2/

Github Repo: https://github.com/coralogix/cloudformation-coralogix-aws/tree/master/opentelemetry/ecs-ec2

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/eb33e6e8-6633-4d81-ae67-ecdedc181048)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/1bb78c43-7a0a-4ca6-8a1f-e1ab68e90aac)

Create stack from cloudformation:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/e1c2d486-c59c-4ed3-92b2-63555ab0308d)

Template file: https://github.com/coralogix/cloudformation-coralogix-aws/blob/master/opentelemetry/ecs-ec2/template.yaml

copy it to local and upload it in stack in cloud formation

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/2f51eee3-f0fc-4df1-818b-7acdd83b43d1)

we can also visualize the services that are going to be created using `view designer`

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/a688f44d-e841-482d-ae4f-f1c3c7d18e88)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/981fc2e9-1650-47bb-b72e-b34bb793d1e4)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/a73d1d59-4a76-41fb-a30c-76f0ae39baa3)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/852944cb-bf5c-49af-99ae-309be124f9db)

Coralogix:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/841d73ec-17c8-4671-a0b2-2665939e6e26)

</details>

<details>
  <summary>4.1,4.2 Coralogix Academy - Introduction to Parsing Rules</summary>
 
![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/76a871ad-2f10-4188-8bee-6d709c3485b2)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/db29c0c6-b90c-4e0d-9f80-54b7493ff8d4)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/008911cf-c0b6-4c22-9cce-7dc0dbcaa000)

</details>

<details>
  <summary> 4.3 Coralogix Academy - Regex Basics </summary>
  
Blog Link: https://coralogix.com/docs/log-parsing-rules/#parse

Best Regex website: https://regex101.com/

</details>

<details><summary>4.4 Parsing rules</summary>

Extract:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/230ee8e0-2421-48a0-8572-6de0b354674c)

JSON Extract:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/5e10ccfc-1cf9-4340-b42e-fa55588cabe8)

Pull severity from AWS-ELB logs:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/0913d0cb-88cb-43c2-a239-8f6738fff85d)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/2843bbc9-1409-461b-ac43-7b3324000c94)

REPLACE: 

- Get rid of password visibility:

  ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/e6086886-9d21-45c6-bdb3-f4ac30a2db1b)

  ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/bb6b47de-5d1e-4a19-99b2-cd4258f25297)

- Get rid of unwanted words like `DATA` here:

  ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/0c711ecf-f9a0-4e9e-af1e-4b0b54e3fc05)  

  ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/abc69e08-9f7e-452b-9de5-e2d3d04f5801)

BLOCK: 
- used for fata cleansing
![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/6391fea2-e1f8-4b77-88f1-d9981da42e67)


If you don't want the logs but just want to see it in S3:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/b903ad14-9b63-4d06-af2e-a3e2d29eea3d)

TIMESTAMP Extract Rule:

1) First parsing

     ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/c5d11ea0-3500-42dd-85bf-366d5743418b)

      ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/0c01406f-d0ad-4630-8051-a57b05bf1cc1)

2) then timestamp extracting
   
  ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/3baac555-d792-4e42-8641-0a8d37f4f50d)
</details>

<details>
  <summary> AWS Enrichment: </summary>

Choose the AWS instance and its key pairs or tags and get insights out of it:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/b8fdb99c-2e43-4a91-a479-fa7d01ed7542)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/9475b6ab-3812-4b87-9954-f7a1cacee556)


</details>

<details>
  <summary> Logging Lucene(Query Language) Tips </summary>
To run a `REGEX` in the search box: we should use `message.keyword: your_regex_pattern` instead of just `message: your_regex_pattern`

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/cc17782c-cbad-48a2-93fb-f50d090c91ba)

Dataprime:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/d6b3ce0b-f537-435c-9339-e5834d6e4ab5)

Search the similar errors in logs that are filtered by Machine learning models under `Templates`:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/4c7c100c-2e76-475a-bcd8-8939a5754c64)

</details>

<details>
  <summary>
    Tracing Tips in coralogix
  </summary>

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/621e2620-4684-448e-a4d3-f465c273fe59)

</details>

<details>
  <summary>
    PromQl 
  </summary>

 ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/8a89c58e-d1a3-4af6-9870-21d8984176f9)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/b09b880a-bed5-4fc6-96e9-c99f7b74c474)

</details>

<details>
  <summary>
    Coralogix K8s Academy - Kubernetes Course Intro
  </summary>

Link: https://coralogix.com/solutions/kubernetes-monitoring/

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/310419a2-a4b6-468b-85f9-147cb0cf9c50)

Nothing specific about Kubernetes but just about metrics and logs of the pods 

</details>

<details>
  <summary>
   [Hands-on] Coralogix AWS Academy - Intro 
  </summary>

Start from here: https://www.youtube.com/watch?v=MsM_fnGpmRo&list=PLponjU1wie0a-vy5teOP1A-X6QyK426FK&index=121&ab_channel=Coralogix

AWS Custom dashboard:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/c2db51ad-7b9b-4844-a056-84463c5b0d46)

Custom Actions:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/84744de8-1bdd-4a7d-9687-677dd63c8210)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/cab9f01f-b7a0-4120-b082-f52abf5f9b77)

Cloudwatch via Firehose Integration: 

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/d4f7240c-2b5d-414a-bbbb-bdba8912702a)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/20816f36-7756-44a8-b49e-3c4cde1f1c59)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/0b8e893e-933d-41de-8535-8d6600d8e05f)

what is Firehose? 

https://aws.amazon.com/firehose/

Setting up Firehose Manually:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/a3c5649c-ce1c-4cad-8656-75ecbedcb2d5)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/3bcd684e-7419-4098-89e2-5fde0fb3a1b6)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/0d5bca86-ab28-4f9e-ab78-e3c290f1b904)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/d8a3ff13-d77a-4ff9-a79f-2ad502b028ba)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/7575b628-6488-4e2b-8feb-f4c9ec06462c)

- Firehose acts like a middleware

Integration: Cloudwatch to Coralogix Firehose:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/ce1d0b2b-aadb-4ca9-ac4e-ecce9d11e8cf)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/94b0af4e-1a08-40db-8d26-7dfdc678a724)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/c20c6a45-f974-4eaa-b11d-7e23f176337d)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/f498919f-702c-42b1-966c-ab2a7fc91d24)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/5a8f5cf2-666a-4c05-ba38-4ccc009adffa)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/a3291c28-5181-4648-9c59-42ca97e5b05e)

### Linking AWS WAF to Firehose:
![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/a405484d-3266-4ff0-a82f-ee427f71ede6)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/7624bfbd-0db1-4608-835c-1619be7203d3)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/49a39e41-31db-4e83-94d1-6fa0283469b3)

- Enable the logging and metrics

  ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/081a9a98-1d7a-47d1-9a49-873a68479a6e)

  ![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/e25eb966-98a5-48e0-8220-64858d468e95)

### Lambda Integration Overview:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/62d52a66-e2e7-46da-9a92-5295af2c1d3e)

### Cloudwatch Logs via the Lambda Shipper:

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/4194611f-14a5-45f8-89a2-969b594bf18c)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/a0d495fd-b696-45c4-a3ec-6b6d7ae9b886)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/1c28566c-715f-4ea7-9231-8ec1c8dc043b)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/b77590db-442a-4e9e-afbd-a94ef06cfee7)

Create `Cloud Formation` creates a auto-populated fields with coralogix 

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/805ca51c-16a8-4aaf-8f4d-17348e625f4c)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/bb91cc64-dd7f-4dae-929a-d4cf3f6e054f)

Once submitted, it will automatically deploy `LAMBDA function` and subscribe to the `log groups`
- Flow: Lambda will be created and then logs will be generated in log groups

### VPC Flow logs Using the Coralogix Lambda Shipper

S3 bucket with VPC flow logs integrated already 

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/9d70b1a8-075a-4c33-aa7b-eb4cc796f92f)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/faafde44-ab21-4626-b372-3bcebedad959)

![image](https://github.com/balajisomasale/Coralogix-Academy/assets/35003840/a1e1ffa0-931e-4681-8ff5-e335c1a76c51)















</details>
