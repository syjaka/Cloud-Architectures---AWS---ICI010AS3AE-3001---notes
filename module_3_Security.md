#h1 Chapter 3. Designing Secure Access to AWS Resources

- AWS responsibilities. The customer is responsible for security inthe cloud.
- AWS is responsible for security ofthe cloud. 
- Security is one of the six pillars of the framework.


-   Design principles
1.  Implement a strong identity foundation. - The principle of least privilege is a key factor Also centralized id management etc...
>  > - Grant only the permissions that are required to perform a task.
>  > - Start with a minimum set of permissions.
>  > - Grant additional permissions as necessary.
>  > - Revoke unnecessary permissions

2.  Protect data in transit and at rest. - Data classification, encryption, access control
>  >Protect data in transit using cryptographic protocols like TLS.
>  > - TLS secures data as it moves between the client and cloud storage.
>  > - Limit access to data and prevent unauthorized access through encryption.
>  > - Protect data both in transit and at rest.
>  > - Data in transit is more vulnerable, making protection critical.
>  > Protect data at rest using encryption within your cloud solution.
>  > - Client-side encryption offers end-to-end protection, covering data in transit and at rest.
>  >  Protecting data at rest with server-side encryption
>  > - Server-side encryption encrypts data before storage.
>  > - Amazon S3 provides server-side encryption, encrypting data at the object level as it is written to disks in AWS data centers and decrypting it upon access.
>  > - Example: Encrypting personal user data, like a Social Security Number, stored in a cloud database.
3. Apply security at all layers.
>  > - defence-in-depth approach
4. Keep people away from data
>  > - reduce or eliminate the need for direct access or manual processing
5. Maintain traceability
>  > - Log and metrics collection ant automated followup
6. Prepare for security events
>  > - prepare ready policies, run simulations, use automation tools to detect, investigate, recover
7. Automate security best practices
>  > - Automated security mechanisms enhance the ability to securely scale quickly and cost-effectively.
>  >   This involves creating secure architectures with controls defined and managed as code in version-controlled templates.


Authenticating and securing access
- Distinguis the difference between authentication and authorization
