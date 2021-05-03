### Create ECS Cluster
    * Update and Push ecs-cloud-formation.yaml with following parameters values.
      1.  VPC - Fetch your Default VPC Id from AWS Console 
      2.  SubnetA - Fetch your Public subnet 1 ID from AWS Subnet Console- Please make sure this Subnet is associated with Default VPC
      3.  SubnetB - Fetch your Public subnet 2 ID from AWS Subnet Console- Please make sure this Subnet is associated with Default VPC
      4.  Image - ARN of your Container Image.
      5.  GitHubToken - ARN of the GIT_TOKEN Parameter present in SSM.
    * Run master-protect-cloud-formation.yaml  Cloud Formation Stack from AWS CLI.
      This will create all the necessary AWS Resources for your Service 
         ``` 
         mangesh@Mangeshs-MacBook-Air ecs-service % aws cloudformation create-stack --stack-name ECSCluster --template-body file://ecs-cloud-formation.yaml --capabilities CAPABILITY_NAMED_IAM
       {
           "StackId": "<STACK-ARN>"
       }

         ```

    * Take a Note of the EndPoint Parameter Created as part of Cloud Formation Stack Execution, This is your {LOAD BALANCER DNS URL} (AWS Cosole --> CloudFormation --> Stacks --> ECSCluster -->Outputs)
