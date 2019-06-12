---
layout: post
title:  "Setting up AWS EC2 instances"
date:   2019-06-03 17:00:00 +0100
categories: aws
---

There are many posts on how to set up remote instances on AWS,
<!-- (see [References](#references) at the end of this post), -->
and this is one
more.  Everybody has their own preferences, or the interface changes a
little bit, or for some reason one operation that
works for one user doesn't for another.  

This post is mainly for my own convenience, as I have been going
through the same process of finding those posts scattered around in my
personal notes too many times.  I also try to add a little bit of
information on things that are not  systematically covered in
tutorials.   

---  

## Console vs CLI
There are two ways to communicate with AWS, either using the web
interface via the "Console", or using a command line interface (CLI)
with `aws-cli`.  In post I will only use the web interface.  


## Accounts
I will cover a little bit more than usual.  

# Signing up to AWS
Go to the [main page][aws] to sign up.  This will create a [root
user][aws-account-root-user].  Note however, [see the
documentation][aws-account-root-user],  

> We strongly recommend that you do not use the root user for your
> everyday tasks, even the administrative ones. Instead, adhere to the
> [best practice][iam-best-practices] of using the root user only to
> create your first IAM user.

Instead, [create an IAM user][aws-create-individual-iam-users], named
e.g. `administrator`, different
from the root user for everyday operations.  [Important
note][aws-iam-console-and-sign-in-page] on IAM user sign-in:  

> To use the AWS Management Console, IAM users must provide their
> account ID or account alias in addition to their user name and
> password. When you, as an administrator, create an IAM user in the
> console, you must send the sign-in credentials to that user,
> including the user name and the URL to the account sign-in page.  


# Signing in to AWS
To sign in, go to  https://aws.amazon.com and click on **Sign In to
the Console** (top right hand corner).  

The sign-in page will be different depending on whether you signed in
as root user or IAM user on your previous session.  
1. If it says **"Root user sign in"** and you want to sign in as root
   user, then you know what to do.  Otherwise click on **"Sign in to a
   different account"** and again you should know what to do.  If not,
   use the special URL for your IAM user created by the root user.  
2. If the sign in page shows **"IAM user name"** but you want to log
   in as root user, look for a link **"Sign-in using root account
   credentials"**.  


## Regions
AWS offers different resources in different
[regions][aws-regions-and-endpoints], named after different
geographical regions.  Depending on your needs, the currency in which
you prefer to pay, or other factors, you may prefer to connect to a
remote instance in a particular region.  

The region in which you are currently working is listed on the right
of the top banner, between your username and the tab **"Support"**,
and you can change it by clicking on it.  

## Amazon EC2
> An Amazon EC2 (for [Elastic Compute Cloud][aws-what-is-amazon-ec2]) is
> a virtual computing environment, known as an instance.  

What we will set up next is an EC2 instance in a particular region.
Find your way to the **EC2 Dashboard**.  

# Generating SSH key pairs  
An ssh key pair can be used for secure authentication when connecting
to a remote instance.  See the
[documentation][aws-connecting-to-your-linux-instance-using-ssh] for more.  


Once you have selected a region, you can generate an ssh key pair for
instances that will be created later.  Alternatively ssh key pairs can
be created in the process of creating the instance.  

From the **EC2 Dashboard**, and under **Resources**, there should be a
link to **Key Pairs**, listing all key pairs which you may have
already created and with instructions to create new ones.  I will
choose to let AWS create a key pair.  Alternatively, generate a key
pair and import the public key to AWS.  Instructions [here
(AWS)][aws-importing-your-own-public-key-to-amazon-ec2] or [here
(fastai)][fastai-create-an-ssh-key-and-upload-it-to-aws].  

Click on **"Create Key Pairs"** and give it a name, e.g. `id_rsa_aws`.
At this point, a file `id_rsa_aws.pem` will automatically download to
your computer containing your *private* key.  This file should be kept
in a safe place.  It is standard to keep in a folder `~/.ssh`.

**Important.**  
Make sure to change the file's permission to:  
```bash
cd ~/.ssh
chmod 400 id_rsa_aws.pem
```
Indeed, this file contains your private key, and it should not be
accessible to anybody else.  In fact, if you try a command on this
file before changing the permissions as above, you will likely get
the following error message:  
```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for '/Users/username/id_rsa_aws.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "/Users/username/id_rsa_aws.pem": bad permissions
```

If you wish to [retrieve the _public_ key from the `.pem`
file][aws-retrieving-the-public-key] and save it locally:
```bash
cd ~/.ssh
ssh-keygen -y -f id_rsa_aws.pem > id_rsa_aws.pub
```



# Payment methods
If you happen to use instances in different regions, and if you wish
to use a different payment method depending on the region, check that
the correct payment method is activated.  For this you need to be
logged in as root user.  Then log back in as IAM user.  



# Limit increase
In case you want to launch a [GPU
instance][aws-recommended-gpu-instances], for example, you may need
to [request a limit increase][aws-service-limits].  
<!-- [request a limit increase][fastai-aws-limit-increase]. -->


# Launching an EC2 instance
Here is the general process of launching an instance.  
- Find your way back to the EC2 dashboard on the AWS console and click
on **"Launch instance"**.  
- Select the [type of instance][amazon-ec2-instance-types] (you can
  filter using the search box).
- Click **"Review and Launch"**.  
- Click **"Launch"**, select a key pair, and click **"Launch
Instances"**.  
- Click **"View instance"** (bottom right hand corner of page), or
  else find your way back to your EC2 dashboard.  
- Wait until the status has turned to green ("running").  

# Finding your instance
Find your way to **EC2 Dashboard** and click on **Running instances**
to view all instances that you have launched, running or not.  Tick
the box of the instance of interest to view its details, in particular
its IP address (when it is running), see below.  

# Viewing all your running instances
This is taken [straight out of
stackoverflow][stackoverflow-viewing-all-running-instances].  
In order to view all running instances in all regions, from the AWS
Console, 
- click on **Services** (top left);  
- find **Networking & Content Delivery** and click on **VPC**;  
- look for a block named **"Running Instances"**, showing you the
  current region;  
- click on **"See all regions"**.  

# Retarting/stopping/terminating your instance
Click on **Actions**, then **Instance State**, and finally
**Start/Stop/Terminate**.  Note that it may take awhile for the
instance to start, stop, or terminate. Check the status on the console
for verification.  

Note that at this point the instance is running but we haven't
connected to it yet.  

## Connecting to your instance
# Instance IPv4 public IP
The instance's IP address is needed in order to connect to it
remotely and it is created once the instance is running.  Note that it
is different each time you *start* the instance.  For emphasis, the
same instance will have different IP addresses if you stop it and
restart it later.  Notice that there is no IPv4 Public IP available
when the instance is not running.  


# Connect to the instance via ssh
Once the instance is running, copy its IPv4 public IP, and in a
terminal enter:

```bash
ssh -i /Users/username/.ssh/id_rsa_aws.pem -L localhost:8888:localhost:8888 ubuntu@<your instance IP>
```

Since this is a different IP, it has to be permanently added to list
of known hosts and you should accept it when prompted.  

A bit of explanation:  
- The option `-i /Users/username/.ssh/id_rsa_aws.pem` gives the path to
  the file containing your _private_ key.  Note that by default `ssh`
  will look for `~/.ssh/id_dsa`, `~/.ssh/id_ecdsa`, `~/.ssh/id_ed25519`
  and `~/.ssh/id_rsa`, and this is why some tutorials do not explicitly
  give this information.  Since we are using a different a different
  format (and file name), we need to specify it.  
- The option `-L localhost:8888:localhost:8888` is for port
  forwarding.  This allows to the jupyter notebook from AWS to your
  computer.  



<!-- # References -->
<!-- - Guide from [fastai][fastai-aws-guide].   -->
<!-- - [AWS guide][aws-guide-dlami] to launch a Deep Learning AMI   -->
<!-- - Recommended [GPU instances][aws-recommended-gpu-instances]  (AWS)   -->
<!-- - [Amazon EC2 instance types][amazon-ec2-instance-types] (AWS)   -->
<!-- - Guide from [Keras][keras-aws-guide] .   -->
<!-- - [Install fastai in any AWS  region][pierre-guillou-install-fastai-on-any-aws-region] by Pierre  Guillou -->
<!-- - [AWS fastai GPU image  setup][reshama-shaikh-aws-fastai-gpu-image-setup] by Reshama Shaikh -->
<!-- - [fastec2][fastec2-post] by Jeremy Howard -->

[fastai-aws-guide]: https://course.fast.ai/start_aws.html
[aws-guide-dlami]: https://aws.amazon.com/getting-started/tutorials/get-started-dlami/
[aws-recommended-gpu-instances]: https://docs.aws.amazon.com/dlami/latest/devguide/gpu.html
[amazon-ec2-instance-types]: https://aws.amazon.com/ec2/instance-types/
<!-- [keras-aws-guide]: https://blog.keras.io/running-jupyter-notebooks-on-gpu-on-aws-a-starter-guide.html -->
[aws-p2-instances]: https://aws.amazon.com/ec2/instance-types/p2/
[aws-pricing]: https://aws.amazon.com/ec2/pricing/on-demand/
[aws]: https://aws.amazon.com
[fastai-aws-limit-increase]: https://course.fast.ai/start_aws.html#step-2-request-service-limit
[iam-best-practices]: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html
[aws-iam-console-and-sign-in-page]: https://docs.aws.amazon.com/IAM/latest/UserGuide/console.html
<!-- [aws-account-root-user]: https://docs.aws.amazon.com/global-accelerator/latest/dg/auth_access_getting-started.html -->
[aws-create-individual-iam-users]: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#create-iam-users
[aws-creating-a-key-pair-using-amazon-ec2]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#having-ec2-create-your-key-pair
[aws-retrieving-the-public-key]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#retrieving-the-public-key
[aws-importing-your-own-public-key-to-amazon-ec2]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#how-to-generate-your-own-key-and-import-it-to-aws
[fastai-create-an-ssh-key-and-upload-it-to-aws]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#how-to-generate-your-own-key-and-import-it-to-aws
<!-- [pierre-guillou-install-fastai-on-any-aws-region]: https://medium.com/@pierre_guillou/guide-install-fastai-in-any-aws-region-8f4fe29132e5 -->
<!-- [reshama-shaikh-aws-fastai-gpu-image-setup]: https://github.com/reshamas/fastai_deeplearn_part1/blob/master/tools/aws_ami_gpu_setup.md -->
[fastec2-post]: https://www.fast.ai/2019/02/15/fastec2/
[aws-account-root-user]: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html
[aws-regions-and-endpoints]: https://docs.aws.amazon.com/general/latest/gr/rande.html
[aws-what-is-amazon-ec2]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html
[aws-connecting-to-your-linux-instance-using-ssh]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html
[aws-service-limits]: https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html
[stackoverflow-viewing-all-running-instances]: https://stackoverflow.com/questions/42086712/how-to-see-all-running-amazon-ec2-instances-across-all-regions/51208275#51208275
