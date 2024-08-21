#  1. Cloud Architecting

## 2. History
- Cloud architecting involves designing well-structured, scalable, and reliable architectures for cloud environments.
- In the early 2000s, Amazon faced challenges in building a scalable and highly available ecommerce service without proper cloud architecture.
- Initial development was slow and complicated due to a lack of centralized planning and reusable resources.
- Amazon resolved these issues by creating well-documented APIs and internal services for scalability and reliability.
- In 2006, Amazon began offering these services to the public as Amazon Web Services (AWS), starting with Amazon SQS, S3, and EC2.

## 3. What is
- Cloud architecture is the practice of applying cloud services and features to meet an organization’s technical and business needs.
- It is similar to constructing a building: a solid foundation (well-architected system) ensures stability and function.
- The process involves the customer outlining business goals, the cloud architect designing the solution (blueprint), and the delivery team implementing it.
- Well-architected systems increase the likelihood of achieving business goals through effective technology solutions.

 ![image](https://github.com/user-attachments/assets/03ec885d-9091-4f41-9e3e-2c5f66f5d233)
- Cloud architects engage with decision makers to identify business goals and needed improvements.
> - They ensure alignment between technology deliverables and business objectives.
> - They collaborate with delivery teams to ensure appropriate technology features are implemented.
> - Cloud architects manage an organization's cloud computing architecture.
> - They develop technical cloud strategies based on business needs, assist with cloud migration, review workload requirements, and address high-risk issues.
> - They work to implement the AWS Well-Architected Framework.

## 4. AWS Well-Architected Framework
   ![image](https://github.com/user-attachments/assets/950ba06b-7fa6-4229-b635-f91d22c5f08d)
- The AWS Well-Architected Framework provides a consistent approach for evaluating and implementing cloud architectures.
- It includes foundational questions and best practices to ensure architectures align with cloud best practices.
- AWS developed the framework after reviewing thousands of customer architectures on AWS.
- The framework is organized into six pillars: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, and Sustainability.
> 1. Operational Excellence 
>  > The Operational Excellence pillar focuses on supporting development, running workloads effectively, gaining operational insights, and continuously improving processes to deliver business value. Related also to the team, not only infra and applications.
> 2. Security 
>  > The Security pillar focuses on protecting data, systems, and assets while leveraging cloud technologies to enhance security. Security is present in all layers of the system.
> 3. Reliability
>  > The Reliability pillar ensures that a workload performs its intended function correctly and consistently when required. - Fail safety
> 4. Performance Efficiency
>  > The Performance Efficiency pillar focuses on using cloud resources efficiently to meet performance requirements and maintaining that efficiency as demand and technologies evolve.
> 5. Cost Optimization
>  > The Cost Optimization pillar emphasizes running systems that deliver business value at the lowest possible cost.
> 6. Sustainability
>  > The Sustainability pillar focuses on understanding and quantifying the environmental impacts of services throughout the workload lifecycle and applying design principles to minimize these impacts when building cloud workloads.

  Using the AWS WA Tool
  - The AWS Well-Architected Tool (WA Tool) is a self-service tool available in the AWS Management Console to help design well-architected solutions.
  - It provides on-demand access to AWS best practices for building secure, high-performing, resilient, and efficient infrastructure.
  - The tool helps review the state of workloads and compare them to AWS architectural best practices.
  - Users define their workload, answer questions in key areas (operational excellence, security, reliability, performance efficiency, and cost optimization), and receive an       action plan for improvement.
  - The tool offers a consistent process to review and measure cloud architectures, minimize system failures and operational costs, and provide best practice guidance.
  - Results from the tool can guide architectural decisions and be integrated into corporate governance processes.

  
## 5. Best practices for building solutions on AWS

Design trade-offs

- Evaluate trade-offs to select an optimal approach.
- Trade consistency, durability, and space for time and latency to achieve higher performance.
- Prioritize speed to market over cost for new features.
- Base design decisions on empirical data in ideal world. In reality might not be achievable in short term. Solution base decisions in best data available.
- Consider how trade-offs can increase cost and complexity.
- Perform load testing and benchmarking to ensure measurable benefits.
- Understand the impact of design choices on customers and workload efficiencies.
- Learn best practices and avoid anti-patterns in AWS solution design.
- Do not trade-off security

Implementing scalability

![image](https://github.com/user-attachments/assets/8b3c12fd-fe5f-4605-aedb-a30d3f9a613a)

- Scale your infrastructure quickly and proactively when running workloads on AWS Cloud.
-  **Implement scalability at every layer of your infrastructure**.
- Use monitoring tools like Amazon CloudWatch to detect when resource thresholds are reached.
- Define thresholds (e.g., 60% CPU utilization for over 5 minutes) to trigger resource scaling.
- Amazon EC2 Auto Scaling launches new instances automatically when an alarm is triggered, ensuring capacity is available before it's needed.
- Design systems to be elastic, reducing costs by not running unnecessary instances when demand drops.
- Reactive and manual scaling can lead to application access issues and delays.

Using IaC

![image](https://github.com/user-attachments/assets/8bc04b08-6916-4d3b-9b7e-efa2da6b523e)
- **Automation is essential in any computing environment.**
- Infrastructure as Code (IaC) is used for infrastructure automation to create environments.
- IaC is commonly used in software development (devOps) to build, test, and deploy applications.
- Deploy duplicate environments rapidly using a single template with IaC.
- IaC eliminates repetitive manual steps and checklists.
- Reduce configuration errors caused by manual configuration through IaC.
- Quickly fix errors by rolling back to the last known stable configuration files.
- Roll back environments using previous IaC configuration files for reasons like deploying older application versions.
- Propagate changes consistently to all stacks by updating the IaC template and pushing changes.

**Treating resources as disposable**
- Treating resources as disposable means viewing infrastructure as software, not hardware.
- Hardware is expensive and inflexible, with difficult upgrades due to sunk costs.
- Treating resources as disposable allows easy migration between instances or resources.
- This approach enables quick responses to capacity changes, application upgrades, and management of underlying software.
- Pets vs cattle.

Using loosely coupled components

![image](https://github.com/user-attachments/assets/9f3433a1-586e-4dbd-9a64-5d8266b090f1)


Designing services, not servers
- Consider using containers or serverless solutions when appropriate.
- Use message queues to handle communication between applications.
- Store static web assets off-server, such as on Amazon S3.
- Manage user authentication and user state storage with AWS managed services.
- Design services, not servers, by using AWS serverless solutions and managed services.
- Serverless solutions like AWS Lambda, Amazon SQS, Amazon DynamoDB, and others can replace traditional server-based solutions at a lower cost and with better performance.

Choosing the right database solution
- Consider read and write needs.
- Assess total storage requirements.
- Evaluate typical object size and nature of access to these objects.
- Determine durability requirements.
- Consider latency requirements.
- Plan for maximum concurrent users to support.
- Understand the nature of queries.
- Ensure the required strength of integrity controls.

- Choose the right database solution based on the specific needs of your application environment.
- AWS recommends selecting a data store based on application requirements rather than hardware or license constraints.

Avoiding single points of failure

![image](https://github.com/user-attachments/assets/ffa2b9ff-c468-4f3e-97d0-ce795e48705f)
- Eliminate single points of failure from your architecture where possible.
- Avoid always duplicating every component; use automated solutions that launch components as needed.
- Utilize managed services to automatically replace malfunctioning hardware.
- A single database server connected to multiple application servers is a single point of failure and should be avoided.
- Ensure application servers continue functioning even if underlying hardware fails.
- Create a secondary (standby) database server and replicate data to avoid single points of failure.
- Design applications to treat resources as disposable and support changes in hardware.

Optimizing for cost

- Take advantage of AWS flexibility to increase cost efficiency.
- Ensure resources are the right size and type for the job.
- Identify and monitor key metrics.
- Turn off resources that are not in use.
- Assess how often each resource will be used.
- Consider replacing servers with managed services.
- Trade fixed expenses for variable expenses with cloud computing.
- Pay only for the services you use for as long as you use them.
- Optimize costs within each service, considering different pricing tiers, models, or configurations.
- Avoid replicating on-premises data center setups running 24/7 in the cloud to build a cost-effective infrastructure.

Using caching

![image](https://github.com/user-attachments/assets/beb6a44e-5862-42c2-a298-8e02da34735e)
- Caching improves performance by temporarily storing data in an intermediary location between the requester and permanent storage.
- The primary purpose of caching is to speed up data retrieval by reducing the need to access slower underlying storage layers.
- Cached data allows future requests to be served faster than accessing the primary storage location.
- Caching enables efficient reuse of previously retrieved or computed data.
- Example: Using Amazon CloudFront in front of Amazon S3 for caching.
  - The initial request checks CloudFront for the file.
  - If the file is not found, CloudFront retrieves it from Amazon S3, stores a copy at a nearby edge location, and sends a copy to the user.
  - Subsequent requests for the file are served from the closer CloudFront edge location, reducing latency and cost.
  - After the first request, there are no additional costs to transfer the file from Amazon S3.

Securing your entire infrastructure
- Build security into every layer of your infrastructure.
- Use managed services for enhanced security.
- Log access to resources for monitoring and auditing.
- Isolate parts of your infrastructure to limit the spread of threats.
- Encrypt data both in transit and at rest.
- Enforce granular access control based on the principle of least privilege.
- Use multi-factor authentication (MFA) for added security.
- Automate deployments to maintain consistent security across your infrastructure.
- Secure individual environments and components from each other.
- Example: Use Amazon EC2 security groups to control traffic flow and reduce the spread of security threats.

## 6. AWS Global Infrastructure
![image](https://github.com/user-attachments/assets/6a2df913-2a8f-4e03-a613-9b87a277927c)
![image](https://github.com/user-attachments/assets/d6fe7f26-7883-459e-9a47-fbebc9a1215d)
![image](https://github.com/user-attachments/assets/d566de65-cd83-4c78-9f77-0500d09e8b33)

- AWS Global Cloud Infrastructure offers 200+ services from data centers worldwide.
- Infrastructure includes 102 Availability Zones in 32 Regions, supporting highly available, scalable, and flexible architectures.
- Choose AWS Regions based on business and workload needs.
- Regions consist of two or more Availability Zones, each with one or more data centers.
- AWS PoPs and regional edge caches reduce latency by keeping data close to customers.
- Regions are connected to multiple ISPs and a private global network backbone for consistent, low-latency cross-Region connections.
- Regions introduced post-March 20, 2019, are disabled by default and must be enabled manually.
- Regions like AWS GovCloud (US) have restricted access for regulatory compliance.
- Regions are isolated for fault tolerance; data is not automatically replicated across Regions.
- Users are responsible for cross-Region data replication based on compliance and latency needs.
- Not all AWS services are available in every Region.
- Availability Zones are isolated locations within a Region, designed as independent failure zones with their own power supplies and connections.
- Users must select Availability Zones for deploying systems, with options to span multiple zones for resilience.
- Local Zones extend AWS services closer to end users in large population and industry centers without existing Regions.
- Use Local Zones for latency-sensitive applications like gaming, media, and machine learning.
- Local Zones are extensions of AWS Regions, providing high-bandwidth, secure connections to in-Region workloads.
- AWS data centers form the foundation of its infrastructure, though specific deployment locations aren't user-defined.
- Data centers are highly available, with automated processes to handle failures and N+1 configurations for load balancing.
- AWS uses custom network equipment from multiple original device manufacturers (ODMs).
- CloudFront's global network includes 410+ PoPs, with 400 edge locations and 13 regional mid-tier caches for reduced latency.
- Edge locations and regional edge caches optimize content delivery, with support for services like Amazon Route 53 and AWS Global Accelerator.
A large architecture:
<img width="794" alt="image" src="https://github.com/user-attachments/assets/9c5ef1b7-3d84-4d43-8b04-e1aa6b90c7fc">


