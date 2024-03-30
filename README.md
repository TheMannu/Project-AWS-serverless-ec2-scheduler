# Serverless EC2 Instance Scheduler for Company Working Hours 
## Scenario :
In some companies, there is no need to run their EC2 instances 24/7; they require instances to operate during specific time periods, such as company working hours, from 8:00 AM in the morning to 5:00 PM in the evening. To address this scenario, I will implement two Lambda functions responsible for starting and stopping instances. These Lambda functions will be triggered by two CloudWatch Events in the morning and evening. This solution is fully serverless.

![Blank diagram](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/c59505e1-947d-46a6-bc0b-690442f0d695)


## Steps :

### Step 1 :
### Creating the Instance :
1. Navigate to the EC2 Console.
2. Follow the Outlined steps below.

![A 2](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/18393246-39a2-422e-a08c-43dd6c8f58f9)


![A 3](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/92c2fc9f-292c-485f-aba3-3138540728fa)


![A 4](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/b569e36d-221b-47d5-ae28-b42ecf7f3099)


![A 5](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/3e83e7eb-c09d-4aac-a851-9db97e86e18d)


![A 6](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/bfdcb79b-f2f2-4135-bb24-7ee063d3089b)


![A 7](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/6fab41a5-1a8c-4877-81f2-30c86e613bac)


### Step 2 :
### Creating the Policy :


1. Navigate to the IAM Console.
2. Click on "Policies" and then Click on "Create policy"


![A 8](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/7f772e4f-57df-48ed-86fb-3affed5d0391)


3. Select services as EC2.
4. And Actions are DescribeInstances , StartInstances.


![A 9](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/a9440779-b3d0-4a57-b0fe-8d34f20765c1)


![A 10](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/1b1f7843-9fb5-47a6-9333-f598ad1e39e5)


![A 11](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/feda1daa-9513-4654-a40f-418e4205235c)


![A 12](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/91756be6-40c8-4e6b-ba61-a49f182264fd)


![A 13](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/33f4ab27-5ee2-409a-b5a5-e028e85467bb)


![A 14](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/94f55bd7-a795-4cc8-85a4-7260a48f72d0)
5. Now we have created a policy for starting instances. We also need to create a policy for stopping the instances. This is because we are going to create two Lambda functions: one for starting and one for stopping the instances. Each function will have its own role, and we will attach these two policies to their respective roles.<br>
6. Now  we are going to repeat the same steps for Creating Stopping Policy also.<br>
7. Everything is same , Except Actions because we are going to stop the instance.<br>
8. The Actions are DescribeInstances , StopInstances .<br>
9. Keep your Plolicy name as "stop-ec2-instance".

## Step 3 :
## Creating the Lambda functions :

1. Navigate to the lambda Console.
2. Follow the Outlined steps below.


![A 15](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/7dc53614-44e4-4d54-b410-134fb2ac7c4a)


![A 16](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/4b24058e-2255-4b89-9045-eb41d3a4ce7f)


![A 17](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/9802aa9b-238e-4f06-9561-ac86847bfa0b)


![A 18](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/42545208-3259-466f-bd85-c040cd7d679e)

![A 19](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/6a481f96-39ce-4bf3-a10e-2894f3af40b1)

![A 20](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/1824252b-7cc5-4809-9e1c-72c8698b9547)

![A 21](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/580ca985-6cd6-4fc5-8eff-5f0dbed8c91b)


![A 22](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/98715282-a7a9-4600-b7d4-c2ffd0d772bf)


![A 23](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/a9235a51-6afd-4772-b26d-9ac867aeb31e)


![A 24](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/c5e48728-40b1-45d5-a2a5-905e4d26c69e)


![A 25](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/2b726bd7-a309-4bb5-9d86-51b7f45e4ce5)


![A 26](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/8af178fe-0421-44d2-b347-6f0a26df9dc6)


![A 27](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/4b9f00d6-08c3-4b78-9872-cf09030412e2)

Now again , go to the Lambda console and then test the code.
![A 28](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/e1ab31a1-a5cb-4495-bc06-823077db56da)


![A 29](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/e845454d-8577-440c-8342-e9ef369ceda2)


3. Now we Created  alambda function for Starting Instance.
4. We have to Reapeat the same steps again to Create a Lambda function for Stopping Instance , Keep your lambda function name as "Stop-EC2-demo".
5. The only changes we have to make are to replace the default code with the 'stop-ec2-instance.py' code and attach the policy we created for stopping instances to the role of this Lambda function.


![A 30](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/909b66e3-7671-476a-8446-43235d3e31b8)

6. As demonstrated above, when I test my Python code, it runs successfully and stops the instance.
7. Now, we are ready to proceed and create schedules for this functions.

### Step 5 :
### Creating the Schedules Using Cloud Watch :

1. Navigate to the Cloud Watch Console.
2. Follow the Outlined Steps below.


![A 31](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/a01e72d2-f4fe-42a6-a742-447f8bec49ed)


![A 32](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/dbae8ae9-1497-4bd1-9ebe-c07fc06098d0)


![A 33](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/82e9114b-fb69-428a-9432-a6e3cd277879)


### Note : Keep your rule name as "start-ec2-rule" , I mistakenly named it 'role' Please do not name it as 'role.'


![B 34](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/a094a0f0-522a-4ddd-8ab7-4deed9bb2105)


![B 35](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/3fc15506-c2ef-4c0c-a1bf-1acfd3134ddd)


![36](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/15470aa3-1ddd-4a92-b613-340e94539641)


![37](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/26ba8e11-975a-4015-83e8-1be76a7b938e)


![38](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/556af812-e3f8-4e80-b46f-159b8cd1d324)


![39](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/fef83eec-6f50-441c-9128-39f5b5fc2213)


![40](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/08643b37-7bf5-4fec-a2fe-aa9a88fb6af5)


![42](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/17a135f4-97dd-4814-989e-f1785276bf29)


![43](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/495d1e01-d0ce-4e57-93f8-a2c1f6d07494)


3. We have now created a schedule for starting the instance every day at 8:00 AM.<br>
4. Next, we need to create a schedule for stopping instances.<br>
5. To create the schedule for stopping instances, follow the same steps as for starting instance scheduling with a few changes, Keep your rule name as "stop-ec2-rule".<br>
6. The changes include modifying the scheduled time and selecting the appropriate scheduling function.<br>
7. We need to change the schedule time to 17:00 because it will stop the Lambda function at 17:00 IST (5:00 PM).
   

![44](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/303b69c5-66a1-4691-8146-b375a7482b9c)


8. We have to Change the Function as Stop-EC2-demo


![B 45](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/c8a48827-bf46-4e30-9ce2-2140fd69e643)


9. Now, we have successfully created two schedules: one to start the instance every day at 8:00 AM and the other to stop the instance every day at 5:00 PM.


![B 46](https://github.com/TheMannu/serverless-ec2-scheduler/assets/84488161/607c6dfa-d8d8-44c3-bb4e-87858227a72c)

