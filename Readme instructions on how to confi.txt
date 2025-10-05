Readme instructions on how to configure the EC2 with teardown instructions

1. After you sign into AWS, you go to EC2
2.on the left side tap type go to security groups (under network and security) and click it
3. once there, click the orange button that says create security group
4.under basic details- give it a name and copy and paste the name under description too
5. Go to inbound rules, click add rule
6. In add rule, under type select HTTP. Under Source select Anywhere-IPv4.
7. Skip Outbound Rules (Never touch it)
8. Go to Tags. It is optional to add a new tag, however, they will be needed moving forward
9. Create group
10. Once create group this will take you to screen that shows it was created successfully
11. Go to the left side and go to Instances and click on instances
12. Click the orange button that says launch instances
13. This will take you to the launch an instance page. Here you go to name and tags and enter a name.
14. Bypass the application and os images and instance type (should be set on t3.micro, if not, select it)
15. Under key (login), select create key pair and name it under key pair name. Keep everything else the same and click create key pair
16. once selected it will download a file-- ignore it
17. Under network settings, go to firewall and select existing security group. In this case, select the security group you create earlier.
18. skip configure storage
19. Go to Advanced details and click it to open it up. Ignore everything and go to the User data - optional
20. Inside the box you will you go to 
https://github.com/balericaclass7/bmc5/blob/main/ec2scrpit and copy the script with the copy raw file
21. Paste this script inside the box.
22. Click the orange button and launch your instance
23. You will go to a screen that says "successfully initiated launch of instance". Within the green box, click the link with instance. It should be numbers and letters.
24. In the next screen there will be a instance summary. Go to Public DNS, copy it. Do not click open address or the small box, just copy it.
25. Open a new browser put in http:// and then paste what you just copied in front of it.
26. Congratulations you should now see AWS Instance Details
Samurai Katana
27. Your EC2/server is now running.

Teardown Instructions

1. Go back to EC2 and on the left side, select instances
2. Select the small box next to the name of your instance. Your instance should say running.
3. Go to instance state and select terminate instance
4. That will terminate your instance.

 