# Go Harbor: A Deep Dive

Often referred to simply as **Harbor**, it is an open-source registry designed for storing, managing, and distributing container images and other cloud-native artifacts. As a project under the Cloud Native Computing Foundation (**CNCF**), it is a robust and well-supported solution.

**Harbor** is especially suitable for enterprise environments because of its comprehensive set of features.

> Harbor is a robust open-source container registry ideal for enterprises due to its comprehensive security features and scalability. As part of the Cloud Native Computing Foundation, it offers image storage, vulnerability scanning, and role-based access control among other features, making it suitable for organizations with strict compliance needs. However, its rich feature set and complexity may be overkill for simpler use cases. Alternatives like Docker Hub, GitLab Registry, AWS ECR, Google Container Registry, and Azure Container Registry may be better suited for different requirements. Installation on Ubuntu, while straightforward, requires attention to setup details and security configurations.

**What I Have to Say About Harbor:**

* **Powerful but Complex:** Harbor is feature-rich, but that also means it can be more complex to set up and manage compared to simpler registries.
    
* **Great for Enterprises:** Its strong focus on security and enterprise features makes it a good fit for organizations with strict compliance requirements.
    
* **Active Community:** The large and active community provides ample resources, documentation, and support.
    
* **Regular Updates:** It receives regular updates and improvements, ensuring it stays relevant in the ever-evolving cloud-native landscape.
    

---

![](https://goharbor.io/img/logos/harbor-horizontal-color.png align="center")

## **Harbor: An Enterprise-Grade Solution**

**Harbor** stands out due to its robust feature set aimed at providing secure, scalable, and enterprise-ready image management. Key highlights include:

* **Comprehensive Features:** **Harbor** offers extensive functionality covering image storage, role-based access control (RBAC), vulnerability scanning, image signing with Notary, replication, garbage collection, and more. This makes it ideal for organizations with demanding security and compliance needs.
    
* **Security Focus:** Harbor prioritizes security through RBAC, vulnerability scanning, content trust, and audit logs, ensuring image integrity and controlling access.
    
* **Open Source and CNCF Project:** Being open source and backed by CNCF guarantees transparency, community support, and long-term sustainability.
    
* **Scalability and Extensibility:** Harbor's architecture allows horizontal scaling for large deployments and supports plugins for custom integrations.
    

%[https://www.youtube.com/watch?v=4zZiBcvZmgQ&t=6s] 

![](https://www.youtube.com/watch?v=4zZiBcvZmgQ&t=6s align="center")

## Feature-Rich:

* **Image Storage and Distribution:** Core functionality for storing, managing, and distributing container images.
    
* **Role-Based Access Control (RBAC):** Granular control over who can access and manage images, enhancing security.
    
* **Vulnerability Scanning:** Integrates with vulnerability scanners to identify security flaws in container images.
    
* **Image Signing and Notary:** Ensures the integrity and authenticity of images using digital signatures.
    
* **Replication:** Supports replicating images across multiple Harbor instances or other registries.
    
* **Garbage Collection:** Automatically removes unused images to free up storage space.
    
* **User Management:** Allows managing users, groups, and their permissions.
    
* **Web UI and API:** Provides a user-friendly interface and API for interacting with the registry.
    
* **Integration with CI/CD Pipelines:** Seamlessly integrates into CI/CD workflows for automated image builds and deployments.
    
* **Helm Chart Support:** Can also be used to store and manage Helm charts.
    
* **Open Source and CNCF Project:** Being open source means it's free to use, modify, and contribute to. Its CNCF backing ensures its long-term sustainability and community support.
    
* **Scalable and Reliable:** Designed for production environments and capable of handling a large number of images and requests.
    
* **Designed for Enterprise:** Offers the features and security required by larger organizations.
    

---

## **Detailed Feature Breakdown**

Here's a more detailed look at some of Harbor's key features:

* **Core Functionality:**
    
    * **Image Storage & Management:** Stores and organizes container images, Helm charts, and other cloud-native artifacts. Supports multiple formats and versions.
        
    * **Registry API:** Provides a standard Docker Registry API (v2), making it compatible with Docker clients and other tools.
        
    * **Multi-Tenancy:** Supports multiple projects (organizations or teams) within a single Harbor instance, each with its own users, access control, and repositories.
        
* **Security:**
    
    * **Role-Based Access Control (RBAC):** Allows fine-grained access control, letting you define different roles and permissions for users and groups at the project and global levels.
        
    * **Vulnerability Scanning:** Integrates with scanners like Trivy to scan container images for security vulnerabilities. Reports and dashboards help you address identified issues.
        
    * **Image Signing & Notary:** Uses Notary to sign images, ensuring their integrity and preventing tampering. This ensures that images come from a trusted source.
        
    * **Content Trust:** Can enforce policies that only allow signed images to be pulled and deployed.
        
    * **Audit Logging:** Tracks all actions performed within the registry, providing audit trails for security and compliance.
        
    * **LDAP/AD Integration:** Integrates with existing LDAP or Active Directory systems for user authentication.
        
* **Replication & Distribution:**
    
    * **Replication Policies:** Enables automated replication of images between Harbor instances or other registries. Useful for multi-region deployments and disaster recovery.
        
    * **P2P Distribution:** Supports P2P image distribution through projects like Dragonfly to reduce the load on the registry and improve image pull speeds.
        
    * **Garbage Collection (GC):** Automatically removes unused or unreferenced images and layers to reclaim storage space.
        
    * **Quota Management:** Set storage quotas for projects to manage disk space usage and prevent overutilization.
        
* **CI/CD Integration:**
    
    * **Webhook Integration:** Supports webhooks to trigger actions when images are pushed or deleted. This allows you to integrate Harbor into your CI/CD workflows for automated image building and deployments.
        
    * **Helm Chart Support:** Allows storing and managing Helm charts alongside container images.
        
* **User Interface (UI):**
    
    * **Intuitive Web UI:** Provides a user-friendly web interface for managing projects, users, images, scanning results, and other aspects of the registry.
        
    * **Customizable Dashboard:** Provides a customizable dashboard for monitoring the status of the registry.
        
* **API Access:**
    
    * **Comprehensive REST API:** Provides a fully documented REST API for programmatic interaction with the registry.
        
* **Performance and Scalability:**
    
    * **High Availability:** Designed for high availability deployments to ensure continuous operation.
        
    * **Scalability:** Supports scaling horizontally by adding more Harbor instances or scaling the underlying database and storage.
        

---

## **Detailed Pros and Cons**

### **Pros:**

* **Robust Feature Set:** Offers a wide array of enterprise-grade features, including RBAC, vulnerability scanning, image signing, replication, and more.
    
* **Security Focused:** Designed with security in mind, providing features like RBAC, vulnerability scanning, content trust, and audit logs to secure your container images and registry.
    
* **Enterprise Ready:** Suitable for large organizations with complex requirements for security, compliance, and scalability.
    
* **Open Source and CNCF Project:** Benefits from the transparency and community support associated with being an open-source project under the Cloud Native Computing Foundation (CNCF).
    
* **Scalability:** Can be scaled horizontally to handle a large number of images, projects, and users.
    
* **Extensibility:** Supports plugins and integrations to customize functionality and connect with other tools.
    
* **Active Community:** Has a large and active community providing extensive documentation and support.
    
* **Regular Updates:** Gets regular updates and improvements, ensuring it stays relevant and secure.
    

### **Cons:**

* **Complexity:** Harbor's rich feature set makes it more complex to set up, configure, and manage compared to simpler registries.
    
* **Resource Intensive:** Can require significant resources (CPU, memory, storage) to run, especially for larger deployments.
    
* **Steeper Learning Curve:** Requires a deeper understanding of container registries and related concepts.
    
* **Overkill for Simple Use Cases:** Might be too heavy and complex for individuals or small teams with basic needs.
    
* **Initial Setup:** The initial setup process can be more involved compared to some simpler registries.
    
* **Potential Cost:** While the software itself is free, running Harbor in a production environment will require infrastructure resources that come with costs.
    

---

## **Best Alternative: Container Registry Options**

While **Harbor** is powerful, it might not be the right fit for every situation. Here are some of the best alternatives to consider, along with their pros and cons:

1. **Docker Registry (Docker Hub / Docker Trusted Registry):**
    
    * **Pros:**
        
        * **Simplicity:** Very easy to set up and use, especially the public Docker Hub.
            
        * **Widely Adopted:** Most developers are already familiar with Docker Hub.
            
        * **Free Tier (Docker Hub):** Offers a free tier for public repositories.
            
        * **Docker Trusted Registry (DTR):** Enterprise-grade registry from Docker with additional features (now part of Docker Desktop).
            
    * **Cons:**
        
        * **Docker Hub Limits:** The free tier has limitations on storage and private repositories.
            
        * **DTR Licensing:** Docker Trusted Registry requires licensing.
            
        * **Fewer Enterprise Features:** Might lack some advanced features compared to Harbor (e.g., more granular RBAC, advanced replication).
            
2. **GitLab Container Registry:**
    
    * **Pros:**
        
        * **Integrated with GitLab:** Seamless integration with GitLab's CI/CD pipelines.
            
        * **Easy to Set Up:** Relatively straightforward to configure if you already use GitLab.
            
        * **Free with GitLab:** Included as part of the GitLab package.
            
    * **Cons:**
        
        * **Tightly Coupled to GitLab:** Best used if you are already using GitLab for source control.
            
        * **Limited Feature Set:** Might not have all the advanced enterprise features of Harbor.
            
3. **Amazon Elastic Container Registry (ECR):**
    
    * **Pros:**
        
        * **Managed Service:** Fully managed by AWS, reducing operational overhead.
            
        * **Scalability:** Scales automatically to handle increased demand.
            
        * **Tight Integration with AWS Ecosystem:** Seamlessly integrates with other AWS services.
            
        * **Security:** Inherits the security features of the AWS platform.
            
    * **Cons:**
        
        * **Vendor Lock-in:** You are locked into the AWS ecosystem.
            
        * **Cost:** Can be more expensive than self-hosted options, especially at scale.
            
4. **Google Container Registry (GCR) / Artifact Registry:**
    
    * **Pros:**
        
        * **Managed Service:** Fully managed by Google Cloud Platform.
            
        * **Scalability:** Designed to scale for large deployments.
            
        * **Integration with GCP:** Well-integrated with other Google Cloud services.
            
        * **Artifact Registry:** Supports various artifacts (not just containers).
            
    * **Cons:**
        
        * **Vendor Lock-in:** You are locked into the Google Cloud Platform.
            
        * **Cost:** Similar to ECR, can become costly with high usage.
            
5. **Azure Container Registry (ACR):**
    
    * **Pros:**
        
        * **Managed Service:** Fully managed by Azure.
            
        * **Scalability:** Highly scalable to meet enterprise demands.
            
        * **Integration with Azure Ecosystem:** Deeply integrated with other Azure services.
            
    * **Cons:**
        
        * **Vendor Lock-in:** You are locked into the Microsoft Azure ecosystem.
            
        * **Cost:** Can be expensive based on storage and usage.
            

---

## **Which Alternative is "Best"?**

The "best" alternative depends on your specific needs and context:

* **For Individual Developers or Small Teams:** **Docker Hub** is a good starting point for ease of use and the free tier.
    
* **For Teams Using GitLab:** **GitLab Container Registry** is a great option due to its seamless integration.
    
* **For Organizations Using Cloud Platforms:** **ECR, GCR/Artifact Registry, and ACR** are excellent choices due to their scalability and managed nature.
    
* **For Organizations Requiring Advanced Features and Control:** **Harbor** is often the preferred choice due to its robustness and feature-rich nature.
    

## **Key Considerations When Choosing a Registry:**

* **Scale:** How many images will you be storing and distributing?
    
* **Security:** What are your security and compliance requirements?
    
* **Integration:** How well does the registry integrate with your CI/CD pipelines and other tools?
    
* **Cost:** What is your budget and how will the registry impact costs?
    
* **Ease of Use:** How easy is it to set up, manage, and use the registry?
    
* **Community and Support:** What level of community support is available?
    

---

## **Harbor Installation on Ubuntu 24.04: A Basic Guide**

This is a basic guide for installing Harbor using Docker Compose on Ubuntu 24.04. This method is suitable for development or test environments. For production, you'll need to consider a more robust deployment.

### **Prerequisites:**

* A clean Ubuntu 24.04 server.
    
* Docker Engine and Docker Compose installed.
    
    * To install Docker on Ubuntu:
        

```bash
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

* Verify Docker is working:
    

```bash
sudo docker run hello-world
```

* To install Docker Compose:
    

```bash
sudo apt install docker-compose
```

* A domain name or IP address that you will use to access Harbor.
    

### **Steps:**

1. **Download Harbor Installer:**
    

```bash
curl -LO https://github.com/goharbor/harbor/releases/latest/download/harbor-offline-installer-v2.10.0.tgz
tar xzvf harbor-offline-installer-v*.tgz
cd harbor
```

2. **Configure harbor.yml:**
    

* Copy the default config file and customize it:
    
    ```bash
    cp harbor.yml.example harbor.yml
    ```
    
* Edit harbor.yml:
    
    ```bash
    nano harbor.yml
    ```
    

3. **Key Parameters to configure:**
    

* **hostname**: This should be your domain name or IP address.
    
* **http.port**: Default is 80, change it if necessary.
    
* **https.port**: Default is 443. For production use, you'll usually want HTTPS.
    
* **ssl.cert and ssl.key**: If using HTTPS, point to your SSL certificate and private key. For testing, you can generate self-signed certificates but this is not recommended for production.  
    You can use **LetsEncrypt** for a valid certificate.
    
* **harbor\_admin\_password**: Set the initial password for the Harbor administrator account.
    
* **database.password**: Set a strong password for the database user.
    
* Example basic configuration:
    
    ```bash
    hostname: your-domain-or-ip
    https:
      certificate: /path/to/your/certificate.crt #Path to the certificate
      private_key: /path/to/your/private.key # Path to the private key
      port: 443
    http:
      port: 80
    harbor_admin_password: strongpassword
    database:
      password: dbstrongpassword
    ```
    

4. **Prepare SSL Certificates:**
    

* If you are going to use the https protocol for production set the `ssl.cert` and `ssl.key` parameters to point to the correct certificates
    
* If you don't have a certificate, for testing purposes you can use a self-signed certificate with these steps:
    
    ```bash
    sudo mkdir -p /etc/harbor/certs
    sudo openssl req -x509 -newkey rsa:4096 -keyout /etc/harbor/certs/harbor.key -out /etc/harbor/certs/harbor.crt -sha256 -days 365 -nodes -subj "/CN=$(hostname)"
    ```
    
* Change the ssl.cert and ssl.key to `/etc/harbor/certs/harbor.crt` and `/etc/harbor/certs/harbor.key`.
    

5. **Install and Start Harbor:**
    

* ```bash
      sudo ./install.sh
    ```
    
    This will start all necessary containers. It can take a few minutes.
    

6. **Access Harbor:**
    

* Open your web browser and go to
*https://your-domain-or-ip*
(or *http://your-domain-or-ip* if you configured for HTTP only).
    
* Log in with username admin and the password set in `harbor.yml`.
    

---

## **Important Notes:**

* **Production Readiness:** This installation is for basic setup. For a production environment, you'll need to consider:
    
    * Using a proper database like PostgreSQL.
        
    * Externalizing storage for registry data.
        
    * Configuring a load balancer.
        
    * Implementing proper backup and disaster recovery strategies.
        
    * Securing the environment with firewalls and network segmentation.
        
* **Docker Compose Version:** Ensure you are using a compatible version of Docker Compose.
    
* **Port Conflicts:** Ensure that the chosen ports (80 and 443) are not already in use on your system.
    
* **Firewall:** Configure your firewall to allow traffic on the ports used by Harbor.
    

---

### **Further Configuration and Customization:**

After installation, you can further configure **Harbor** through its web interface or by editing `harbor.yml` and using `sudo docker-compose up -d` to restart the service.

You might need to consult the official **Harbor** documentation to understand more advanced configurations and customization options.

[Official Website](https://goharbor.io/)

---

## **In Conclusion:**

**Harbor** is a powerful, feature-rich, and enterprise-grade container registry that excels in environments with stringent security and compliance needs. However, it might be overkill for simpler use cases. Understanding your own requirements and exploring the alternatives will help you choose the best container registry for your projects.
