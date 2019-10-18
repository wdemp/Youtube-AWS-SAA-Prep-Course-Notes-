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
      Infrequent Access: is both fast and cost effective. 
      
