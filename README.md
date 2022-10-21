# Terraform-AWS-Autoscaling
Terraform AWS Autoscaling

````
terraform init
terraform plan
terraform apply
````

Autoscaling the EC2 instance with Load Testing

Now that you verified the Autoscaling group/policy and related components are set up correctly, it’s time to test if the Auto Scaling features work. How? By adding load on the instance recently launched with the AutoScaling group.

1. Open the AWS EC2 instance launched with the Autoscaling group using an SSH client.

2. Next, launch the terminal, and run the below command to install the load stress tool (stress-ng). The stress tool allows you to define and generate the stress on the Ubuntu machine.

````
sudo apt install stress-ng
````

3. Run the stress-ng command below to generate the stress load on the instance.

The below command contains the following flags:

--cpu �tes the number of cores on which load will be generated.
-v – Enables verbose mode.
--timeout – Specifies the time for which load should be generated.

````
sudo stress-ng --cpu 4 -v --timeout 3000s
````
