import boto3

import json

 

AWS_LAMBADA_FUNCTION='arn:aws:lambda:us-east-1:13737373737:function:test'

ACCESS_KEY='XXX'

SECRET_KEY='YYY'

 

lambda_payload = {"name":"name","age":"age"}

print(lambda_payload)

lambda_client = boto3.client("lambda",region_name='us-east-1',

        aws_access_key_id=ACCESS_KEY,

        aws_secret_access_key=SECRET_KEY)

 

resp = lambda_client.invoke(FunctionName=AWS_LAMBADA_FUNCTION,

                            InvocationType='RequestResponse',

                            LogType='None',

                            Payload = json.dumps(lambda_payload))

print(f"resp = {resp}")
