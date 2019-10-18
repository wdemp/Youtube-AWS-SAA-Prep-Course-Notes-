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
     Versioning is a prerequisite that needs to be enabled in order for Cross Region Replication to work. 
