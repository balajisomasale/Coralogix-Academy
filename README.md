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
    Connecting Coralogix to your S3 Archive
  </summary>

An important note is that we need to be the same region: coralogix domain and 

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
