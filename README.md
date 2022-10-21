# Terraform-AWS-Autoscaling
## Building the Terraform Configuration for an AWS Autoscaling Group

The code in file main.tf creates an autoscaling launch configuration (web_config) and provisions an Autoscaling group (autoscalegroup). The Autoscaling group also comes with its components (aws_autoscaling_schedule and aws_autoscaling_policy).

To provision the AWS Autoscaling group, like all other Terraform configurations, Terraform uses three commands in sequence (terraform init, terraform plan, and terraform apply).

##  Autoscaling the EC2 instance with Load Testing

Now letstest  if the Auto Scaling features work by adding load on the instance recently launched with the AutoScaling group.

1. Open the AWS EC2 instance launched with the Autoscaling group using an SSH client.

2. Next, launch the terminal, and run the below command to install the load stress tool (stress-ng). The stress tool allows you to define and generate the stress on the Ubuntu machine.

````
sudo apt install stress-ng
````

3. Run the stress-ng command below to generate the stress load on the instance.

The below command contains the following flags:
````
--cpu  		Denotes the number of cores on which load will be generated
-v 		Enables verbose mode
--timeout  	Specifies the time for which load should be generated.
````

````
sudo stress-ng --cpu 4 -v --timeout 3000s
````
