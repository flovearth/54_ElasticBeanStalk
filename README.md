## Part 1 - Launch an Application

- First download the php-v1.zip and php-v2.zip files from GitHub and share them via Slack.

- Go to `Elastic Beanstalk` service on AWS console.

- Click `Create Application`.

- Enter your application name `MySampleApp`.  (You can also add Application tags if you need.)

- Select `PHP` for Platform, `PHP 7.4 running on 64bit Amazon Linux 2` for Platform Branch and `3.1.2 (Recommended)` for Platform Version.

- Select `Upload your code` for Application code.

- Type `mysampleapp-source-V1` for Version label and select Local file. Then click choose file and upload php-v1.zip file.
  Check File successfully uploaded to be sure.

- Click `Create applicaiton`.

- Wait for Elastic Beanstalk to create the environment for the application. Show the resources being created and listed on the console.

- After the creation of the environment click the link (Application URL) and show the Web Page.

- From the left-hand menu show the app and env menus, talk about them. Click on the tabs like `Configuration`, `Monitoring` etc. and explain them.

- Go to `EC2` service on AWS console and show the resources (Instances, Load Balancers, ASG's etc.) created by Elastic Beanstalk.


## Part 2 - Update the Application

### Step 1 - Update the Application


- Go to `Elastic Beanstalk` service on AWS console.

- Click `Mysampleapp-env` on the left hand menu, and click `Upload and deploy` to update the application. (You can also click `Application versions` on the left hand menu, and then click `Upload` to update but you have to deploy it manually)

- Click `Choose file` and upload php-v2.zip file. Type `mysampleapp-source-V2` for Version label and then click `Deploy`.

- Wait for Elastic Beanstalk to update the application.

- After the update completed click the link (Application URL) and show the Updated Web Page.

- Click `Mysampleapp` >> `Application versions` and show we have one app but two versions.

### Step 2 - Connect to the EC2 instance hosting the App 


- Click `Mysampleapp-env` >> `Configuration` on the left hand menu, from `Security` Category click `Edit`.

- `Virtual machine permissions` >> `EC2 key pair` select your key pair and click `Apply`.

- Go to `EC2` service on AWS console.

- Copy the Public IP of the instance (Launced by Elastic Beanstalk).

- Open your terminal and connect to the instance.

## Part 3 - Terminate the Environment

### Step 1 - Terminate the Environment

- Go to `Elastic Beanstalk` service on AWS console.

- Click `Mysampleapp-env` on the left hand menu, from the Actions select `Terminate environment`. (You can also click `Environments` on the left hand menu, select `Mysampleapp-env` and then from the Actions select `Terminate environment` to delete AWS resources.)

- Read the confirmation message and type the name of the environment into the box and click `Terminate`.

- Wait for Elastic Beanstalk to terminate the environment and show events in `Recent events`.

### Step 2 - Restore Environment

- Click `Environments` on the left hand menu, select terminated `Mysampleapp-env` and then from Actions menu select `Restore`.
  `(The terminated environment will remain visible for about an hour.)`

- Show the environment is deployed and working again. 

### Step 3 - Delete Application

- Click `Applications` on the left hand menu, select `MySampleApp`. From `Actions` menu select `Delete application`. Enter the name of the application to confirm and click `Delete`.

- Wait for a while and show both the environment and the application is deleted.
