Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      ImageId: ami-12345678  # Specify the ID of the desired Amazon Machine Image (AMI)
      InstanceType: t2.micro  # Specify the desired instance type
      KeyName: my-key-pair  # Specify the name of the key pair used to access the instance
      SecurityGroupIds:
        - sg-12345678  # Specify the ID(s) of the security group(s) for the instance
      SubnetId: subnet-12345678  # Specify the ID of the subnet where the instance should be launched
