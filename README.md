Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      ImageId: ami-06ca3ca175f37dd66 
      InstanceType: t3.micro  
      KeyName: Mykeypairname
      SecurityGroupIds:
        - !Ref MySecurityGroup  
      BlockDeviceMappings:
        - DeviceName: /dev/sda1
          Ebs:
            VolumeSize: 8  
            VolumeType: gp2  
      
  MySecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupDescription: My security group
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: 22
          ToPort: 22
          CidrIp: 0.0.0.0/0  
      
Outputs:
  InstanceId:
    Value: !Ref MyInstance
