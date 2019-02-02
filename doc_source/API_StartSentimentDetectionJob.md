# StartSentimentDetectionJob<a name="API_StartSentimentDetectionJob"></a>

Starts an asynchronous sentiment detection job for a collection of documents\. use the [DescribeSentimentDetectionJob](API_DescribeSentimentDetectionJob.md) operation to track the status of a job\.

## Request Syntax<a name="API_StartSentimentDetectionJob_RequestSyntax"></a>

```
{
   "[ClientRequestToken](#comprehend-StartSentimentDetectionJob-request-ClientRequestToken)": "string",
   "[DataAccessRoleArn](#comprehend-StartSentimentDetectionJob-request-DataAccessRoleArn)": "string",
   "[InputDataConfig](#comprehend-StartSentimentDetectionJob-request-InputDataConfig)": { 
      "[InputFormat](API_InputDataConfig.md#comprehend-Type-InputDataConfig-InputFormat)": "string",
      "[S3Uri](API_InputDataConfig.md#comprehend-Type-InputDataConfig-S3Uri)": "string"
   },
   "[JobName](#comprehend-StartSentimentDetectionJob-request-JobName)": "string",
   "[LanguageCode](#comprehend-StartSentimentDetectionJob-request-LanguageCode)": "string",
   "[OutputDataConfig](#comprehend-StartSentimentDetectionJob-request-OutputDataConfig)": { 
      "[S3Uri](API_OutputDataConfig.md#comprehend-Type-OutputDataConfig-S3Uri)": "string"
   }
}
```

## Request Parameters<a name="API_StartSentimentDetectionJob_RequestParameters"></a>

For information about the parameters that are common to all actions, see [Common Parameters](CommonParameters.md)\.

The request accepts the following data in JSON format\.

 ** [ClientRequestToken](#API_StartSentimentDetectionJob_RequestSyntax) **   <a name="comprehend-StartSentimentDetectionJob-request-ClientRequestToken"></a>
A unique identifier for the request\. If you don't set the client request token, Amazon Comprehend generates one\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `^[a-zA-Z0-9-]+$`   
Required: No

 ** [DataAccessRoleArn](#API_StartSentimentDetectionJob_RequestSyntax) **   <a name="comprehend-StartSentimentDetectionJob-request-DataAccessRoleArn"></a>
The Amazon Resource Name \(ARN\) of the AWS Identity and Access Management \(IAM\) role that grants Amazon Comprehend read access to your input data\. For more information, see [https://docs.aws.amazon.com/comprehend/latest/dg/access-control-managing-permissions.html#auth-role-permissions](https://docs.aws.amazon.com/comprehend/latest/dg/access-control-managing-permissions.html#auth-role-permissions)\.  
Type: String  
Length Constraints: Minimum length of 20\. Maximum length of 2048\.  
Pattern: `arn:aws(-[^:]+)?:iam::[0-9]{12}:role/.+`   
Required: Yes

 ** [InputDataConfig](#API_StartSentimentDetectionJob_RequestSyntax) **   <a name="comprehend-StartSentimentDetectionJob-request-InputDataConfig"></a>
Specifies the format and location of the input data for the job\.  
Type: [InputDataConfig](API_InputDataConfig.md) object  
Required: Yes

 ** [JobName](#API_StartSentimentDetectionJob_RequestSyntax) **   <a name="comprehend-StartSentimentDetectionJob-request-JobName"></a>
The identifier of the job\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 256\.  
Pattern: `^([\p{L}\p{Z}\p{N}_.:/=+\-%@]*)$`   
Required: No

 ** [LanguageCode](#API_StartSentimentDetectionJob_RequestSyntax) **   <a name="comprehend-StartSentimentDetectionJob-request-LanguageCode"></a>
The language of the input documents\. You can specify English \("en"\) or Spanish \("es"\)\. All documents must be in the same language\.  
Type: String  
Valid Values:` en | es | fr | de | it | pt`   
Required: Yes

 ** [OutputDataConfig](#API_StartSentimentDetectionJob_RequestSyntax) **   <a name="comprehend-StartSentimentDetectionJob-request-OutputDataConfig"></a>
Specifies where to send the output files\.   
Type: [OutputDataConfig](API_OutputDataConfig.md) object  
Required: Yes

## Response Syntax<a name="API_StartSentimentDetectionJob_ResponseSyntax"></a>

```
{
   "[JobId](#comprehend-StartSentimentDetectionJob-response-JobId)": "string",
   "[JobStatus](#comprehend-StartSentimentDetectionJob-response-JobStatus)": "string"
}
```

## Response Elements<a name="API_StartSentimentDetectionJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [JobId](#API_StartSentimentDetectionJob_ResponseSyntax) **   <a name="comprehend-StartSentimentDetectionJob-response-JobId"></a>
The identifier generated for the job\. To get the status of a job, use this identifier with the [DescribeSentimentDetectionJob](API_DescribeSentimentDetectionJob.md) operation\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 32\.  
Pattern: `^([\p{L}\p{Z}\p{N}_.:/=+\-%@]*)$` 

 ** [JobStatus](#API_StartSentimentDetectionJob_ResponseSyntax) **   <a name="comprehend-StartSentimentDetectionJob-response-JobStatus"></a>
The status of the job\.   
+ SUBMITTED \- The job has been received and is queued for processing\.
+ IN\_PROGRESS \- Amazon Comprehend is processing the job\.
+ COMPLETED \- The job was successfully completed and the output is available\.
+ FAILED \- The job did not complete\. To get details, use the [DescribeSentimentDetectionJob](API_DescribeSentimentDetectionJob.md) operation\.
Type: String  
Valid Values:` SUBMITTED | IN_PROGRESS | COMPLETED | FAILED | STOP_REQUESTED | STOPPED` 

## Errors<a name="API_StartSentimentDetectionJob_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
An internal server error occurred\. Retry your request\.  
HTTP Status Code: 500

 **InvalidRequestException**   
The request is invalid\.  
HTTP Status Code: 400

 **TooManyRequestsException**   
The number of requests exceeds the limit\. Resubmit your request later\.  
HTTP Status Code: 400

## See Also<a name="API_StartSentimentDetectionJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/comprehend-2017-11-27/StartSentimentDetectionJob) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/comprehend-2017-11-27/StartSentimentDetectionJob) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/comprehend-2017-11-27/StartSentimentDetectionJob) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/comprehend-2017-11-27/StartSentimentDetectionJob) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/comprehend-2017-11-27/StartSentimentDetectionJob) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/comprehend-2017-11-27/StartSentimentDetectionJob) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/comprehend-2017-11-27/StartSentimentDetectionJob) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/comprehend-2017-11-27/StartSentimentDetectionJob) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/comprehend-2017-11-27/StartSentimentDetectionJob) 