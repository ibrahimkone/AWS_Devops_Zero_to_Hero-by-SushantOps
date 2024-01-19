 ## Create a bucket:

aws s3 mb s3://my-bucket-name 

## • List buckets: 

aws s3 ls  

## • Delete a bucket: 

aws s3 rb s3://my-bucket-name 

• Upload a file: aws s3 cp my-file.txt s3://my-bucket-name

• Download a file: aws s3 cp s3://my-bucket-name/my-file.txt . 

• List objects in a bucket: aws s3 ls s3://my-bucket-name

• Delete an object: aws s3 rm s3://my-bucket-name/my-file.txt 

• List object versions: aws s3api list-object-versions --bucket my-bucket-name 

• Restore a previous object version: aws s3api copy-object --copy-source my-bucket-name/my-file.txt --key my-file.txt --version-id VersionId --bucket my-bucket-name 

• Grant read access to a user: aws s3api put-object-acl --bucket my-bucket-name --key my-file.txt -grant-read emailaddress=user@example.com 

 • Sync a local directory to a bucket: aws s3 sync my-local-directory s3://my-bucket-name 

 • Move an object within a bucket: aws s3 mv s3://my-bucket-name/old-key s3://my-bucket-name/new-key  
 
 • Generate a pre-signed URL: aws s3 presign s3://my-bucket-name/my-file.txt 
