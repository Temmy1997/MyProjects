* Create the VPC 
* Creates the private and public subnets in the same avalability zone. 
    * NOTE: Make sure you enable the auto assign public ip for the public subnets. 
* Create another public subnet in another AZ.
    * NOTE: We are creating another public subnet because we want to use Application Load Balancer
    *   Application Load balancer requires more than two subnet to be created. 
* Create internet gateway for the public subnet ans attach the internet gateway to the created VPC 
* Create Nat gateway for Private subnet
* Create 2 route Tables for Private and Public Subnet
    * Edit the route in the Route Table 
        - Public Route: Make the TARGET the internt gateway and make the DESTINATION to be the internet(0.0.0.0)
        - Private Route: Make the TARGET the nat gateway and make the Destination the internet (0.0.0.0)
* Attach each subnet to the subnet association of the route table.
* Create 2 security groups(SG)
    * Load Balancer SG
        - Leave the default outboud rules 
        - Edit the inbound rules to allow all traffic to talk to the internet (0.0.0.0)
    * Webserver SG
        - Leave the default outbound rules
        - Edit the inbound to SSH traffic to talk to the VPC 
        - All traffic to talk to the load balancer SG
* Create the EC2 Instance
* Create 


* Create the autoscaling group and attach the lauch configuration to the autoscaling group 