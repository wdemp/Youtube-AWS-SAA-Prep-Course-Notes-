Youtube AWS SAA Course Notes:

Storage: 
-object level storage
-S3 and Glacier 
-Block Level Storage
-EBS Storage
Databases
 -RDS, DynamoDB, Aurora, Redshift
 
 Reliable Storage S3- High Durability and Availability
-S3 object- Bucket
The object is uploaded to S3 and stored in multiple objects in order to ensure high durability and high availabilty. 
* Advantages of S3 are:
    -If any one device fails the object would still be present on another device.
    -This is only applicable to a certain region.
    -For disater recovery, in case of failure in a region, you will need to enable Cross Region Replication for the bucket so that the object can automatically be replicated in another destination region.
     -Versioning is a prerequisite that needs to be enabled in order for Cross Region Replication to work. With Versioning you will be able to keep multiple variants of the object in the bucket in case of application failure or accidental deletion. If another gets overwritten, Versioning will allow the user to restore to a previous version.
     Glacier:
     - used for achieving data 
     - vey cost effective
     There are multiple levels of Retrievel; each with different prices and data delivery speeds.
     -Standard Retrievel- very cost effective, very slow data speeds; typically between 3-5 hours
      Expediated Retrieval: get the objects back in a few minutes and pay alot of money for the speed of the delivery of the data
      Infrequent Access: 
      -is both fast and cost effective. Infrequent Access costs 20% less than Standard S3 IA. This is due to the data not being saved and stored over multiple Availabilty Zones and only being stored in 1 Az. 
      Key Features of Infrequent Access:
      -Same low latency and high throughput performance of S3 Standard.
      -Designed for durability of 99.999999999% of objects across multiple AZ's
      -Resilient against events that impact an entire AZ
      -Data is resilient in the event of one entire AZ destruction
      -Designed for 99.9% availability over a given year
      -Backed with the Amazon S3 Service Level Agreement for availability.
      - Support SSL for data in transit and encryption of data at rest
      - S3 Lifecycle management for automatic migration of objects to other S3 Storage Classes


Amazon Glacier: 

    - Desigend for durability of 99.999999999% of objects acrosss multiple AZs
    -Data is resilient in the event of one entire AZ destruction.
    -Supports SSL for data in transit and encryption of data at rest
    -Low-cost design is ideal for long term archive
    -Configurable retrieval times, minutes to hours
    -S3 PUT API for direct uploads to S3 Glacier, and S3 Lifecycle management for automatic migration of objects.
    
    S3 Glacier Deep Archive: the lowest cost storage and supports long term retention and digital preservation for data that may accesssed once or twice in a year.
    
    Key Features:
     - Designed for durability of 99.999999999% of objects across multiple AZs
     -Lowest cost storage class designed for long term retention of data will be retained for 7-10 years.
     -Ideal alternative to magnetic tape libraries.
     - Retrieval time within 12 hours.
     - S3 PUT API for direct uploads to S3 Glacier Deep Archive and S3 Lifecycle management for automatic migration of objects.
     Storage: choosing permanent storage + Design cost optimized storage- EBS volumes 
     -General Purpose SSD
     -Provisoned IOPS
     -Throughput Optimized HDD
     -Cold HDD
    when to use specific storage models:
  
 
    EC2                        Cost effective volume 
    Web Server                 Volume Type
    Predcitable Workload       General Purpose SSD
    
    typically used for web servers, where you don't have much Input/Output sevices 
    
    database server vs web server: the difference is that the web server sends you to the web pages you rwuest; while   database server sends you to files or programs that are already currently residing in the current network. The databse server works on the client server architecture.
    
    More on Storage- EBS Volumes
    
     EC2 Instance 
     
    
