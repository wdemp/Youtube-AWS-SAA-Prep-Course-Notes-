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
    
    database server vs web server: the difference is that the web server sends you to the web pages you rwuest; while   database server sends you to files or programs that are already currently residing in the current network. The databse server works on the client server architecture. In addition databse servers the read or write option for both of them. The database servers have to search for the file or command that is entered so the process is a litle more complex than the web server. 
    
    More on Storage- EBS Volumes
    
     EC2 Instance                                          Database   - Select Statements ( Read Options)                          
     Database Server                                         |        -Update, Insert and Delete(Write Options)
     Resource Intensive                                      |-Volumes   -Select- search for the data
                                                                         - Update,Insert of Delete-Needs to Write data
                                                                         -I/O controller- takes a lot of strain for these                                                                                operations. 
                                                                         -If there is too much read and write,lagging begins                                                                              to occur and the performance drops. When this occurs the best option would be to choose a Provisioned IOPS 
    
     High Number of Input and Output Operations 
     
     Choosing Performance and Size - EBS Volumes
     
     EC2        ------------Larger in Size           
     Processing Server       Stream in videos
     Processing Videos       High Throughput
     
     The EBS volume that would be needed in this sceneario would be a Throughput Optimized HDD- 400Mibs/
     
     Cold HDD- this is best used for infrequently accessed data- optimized for throughput
     Use Case Scenario- user uploads videos. The video gets stored on EBS volumes. They are accessed over a period of 2 months quite frequently after which they are accessed less frequently.
     Have 2 Seperate Volumes: Store the videos for 2 months on the Throughput Optimized HDD. After 2 months have a script which transfers teh videos to Cold HDD.

Databases: 
Realtional Databases:- When will you choose to use this srevice?
Scenario: You have an Oracle workplace database that is on premise. You want to migrate the data as it is without any hassle or headaches. You use the RDS Oracle. You would use the database migration services from AWS. 
   3rd party application: This has dependency that it only works with certain database engines.  For example: Wordpress only works with Postgres  
   
   Skillset of Developers: They don't know DynamoDB. They aren't up to speed and you don't have the funding to train them. If however they know MySQl well, you can that.
   Structured Data, lot of table joins- choose RDS, not Dynamo DB. 
