$ aws configure

$ aws configure --profile exampleprofilename


$ cat ~/.aws/config

[default]

region = us-eas-1

$ cat ~/.aws/credentials 

[default]

aws_access_key_id = ---------------

aws_secret_access_key = ---------------------------------

---------------------------------------------------


export AWS_PROFILE=dev

export AWS_DEFAULT_REGION=us-ueast-2

---------------------------------------------------

aws [options] <command> <subcommand> [params]
  
AWS ec2 describe-instance --instance-ids i-0564616545
  
aws --profile prod s3 ls
  
aws --region us-east-1 rds describe-db-instances
 
aws guardduty list-findings --detector-id da489798489
  
aws elbv2 create-load-balancer --name myprettyelb
  
--------------------------------------------------
 
 $ aws s3 help
  
 $ aws s3 mb help
  
--------------------------------------------------

  --filter
  
  --query
  
  --output text
  
  $ (command substitution)
  
  bash_functions () {}
  
  
  
  
  
  
  
  
  
  
  
