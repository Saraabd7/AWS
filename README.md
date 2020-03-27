### AWS Production Environment 💾

* S3 service is a storage .

* EC2 service allows you to create a vm .

* IAM service – creates credentials .

* VPC – creates a virtual cloud for networking .

## EC2
The location of this is important as different servers serve different purposes around the globe.
-  Running instances .

-  Launch instance. 

-  Different distributions are available to use.

-  Different processors to choose from.

-  Configuring instance details.( Network - DevOpsStudent - Subnet - DevOpsStudentSubnet)

-  Adding storage

- Add tag, add a new tag (key: name, Cohort:Eng54)
-  Configure security group (allows  to configure what can do from what IP.
- Port 22 – communicates through ssh, do not have the ssh open to the world so change the source to my IP 
- Select existing security groups as they have been set up.
- Creating a new group can have many rules. 
-  In the Launch tab, key pair is about linking public and private keys stored.
- When creating a new key, it will download a key and  would want to put it where all the other keys are stored.  C:\Users\sara.ssh 


## SSH connection
- In the terminal Check on machine that have the ssh key. 


```
  ssh -i ~/< key name > ubuntu@ o eg . ssh -i ~/.ssh/name.pem ubuntu@(my_ip)
```
```
  scp -r -i ~/.ssh/Sara-eng54.pem app ubuntu@my_ip:/home/ubuntu/app
```

```
  sudo apt-get install npm
  sudo npm start
```

## Provision the machine:
- atom. into the starter code given 
- The provision scripts in environment/ app and db there are two files. 
- Check that both the provision scripts have executable writes by cd into them and using the command ll. 


## How to copy a file

```
  scp -i path/to/key file/to/copy user@ec2-xx-xx-xxx-xxx.compute-1.amazonaws.com:path/to/file/

```

```
scp -i ~/.ssh/name.pem ../environment/app/provision.sh ubunutu@ my_ip:/home/ubuntu/file.sh

```
- In ubuntu machine/environment check if the path created the file correctly and then run the provision
to run the file: 

```
./provision.sh

```


## How to copy a directory
- To copy an entire directory, add the -r recursive option:

 ```
 scp -i path/to/key -r directory/to/copy user@ec2-xx-xx-xxx-xxx.compute-1.amazonaws.com:path/to/directory.

 ```


 ``` scp -i ~/.ssh/name.pem -r ../environment/ ubuntu@my_ip:/home/ubuntu/'
```

- In ubuntu machine/environment check if the path created correctly and then run the provision
to run the file: ./

## How to change the rights of a file
If a provision file is not executing you may not have the rights to do this. So either on your local machine or on vm,  into the path where the .sh provision file is stored and run this command:


```
chmod +x

```
 The x is for executable, it adds the right to execute, can do this for read and write too.

* -i refers to the "identity file", which is the key that you use to connect to the AWS server.

* -r is "recursive", which is required for directory sharing this will make sure each file is sent to the new location.
