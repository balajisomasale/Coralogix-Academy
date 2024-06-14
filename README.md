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

<details><summary>4.4 Parsing rules: Parse</summary>

</details>
