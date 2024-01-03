

# AWS SDK integrations

Integrate other services inside step function

1. Step function:

`arn:aws:states:::aws-sdk:sfn:startExecution`

Reference: https://docs.aws.amazon.com/step-functions/latest/dg/supported-services-awssdk.html

## Task state

```
"Resource":"arn:aws:states:::lambda:invoke"
"Resource": "arn:aws:states:::sns:publish",
```
```
"Resource":"arn:aws:states:::lambda:invoke.waitForTaskToken"
```
```
"Resource":"arn:${AWS::Partition}:states:::sqs:sendMessage.waitForTaskToken"
"Parameters":{
            "FunctionName":"arn:aws:lambda:us-east-1:123456789012:function:get-model-review-decision",
            "Payload":{  
               "model.$":"$.new_model",
               "token.$":"$$.Task.Token"
            },
```

## Map state