# PythonAutomateAWS

Using Python to Automate AWS Services 


This is used to create a tag when someone makes a new e3 instance. This uses e3, aws bridge.


import json
import boto3

ec2 = boto3.client('ec2')

def lambda_handler(event, context):
   print(event)

    user=event['detail']['userindentity']['username']

    #InstanceID on what we created
    instance = event['detail']['responseElements']['instancesSet']['items'][0]['instanceId']

    client.create_tags(
        Resources=[
            instanceId
        ],
        Tags=[
            {
                'Key': 'Owner',
                'Value': user
            },
        ]
    )

return
