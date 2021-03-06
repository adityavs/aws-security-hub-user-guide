# Terminology and concepts<a name="securityhub-concepts"></a>

This topic describes the key concepts in AWS Security Hub to help you get started\.

**Account**  
A standard Amazon Web Services \(AWS\) account that contains your AWS resources\. You can sign in to AWS with your account and enable Security Hub\. You can also invite other accounts to enable Security Hub and become associated with your account in Security Hub\. If your invitations are accepted, your account is designated as the Security Hub *master* account, and the added accounts are *member* accounts\. With the master account, you can view findings in member accounts\.  
An account cannot be both a Security Hub master account and a member account at the same time\. An account can accept only one membership invitation\. Accepting a membership invitation is optional\.  
For more information, see [Master and member accounts in AWS Security Hub](securityhub-accounts.md)\.

**Archived finding**  
A finding that has a `RecordState` set to `ARCHIVED`\. Finding providers can archive findings\. Security Hub also automatically archives findings after 90 days\. Archived findings are excluded from the default view of findings lists in the Security Hub console\.  
Archived findings are not deleted\. You can modify the filter applied to a list of findings to display only the findings that you want to see\. To view only archived findings, update or replace the filter applied to the page to `RecordState EQUALS ARCHIVED`\.  
The [https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetFindings.html](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetFindings.html) operation of the Security Hub API returns both active and archived findings\. To return findings that match specific criteria, use filters in your request\. For example, to retrieve archived findings:  

```
"RecordState": [ 
    { 
        "Comparison": "EQUALS",
        "Value": "ARCHIVED"
    }
],
```

**AWS Security Finding Format**  
A standardized format for the contents of findings that Security Hub aggregates or generates\. The AWS Security Finding Format enables you to use Security Hub to view and analyze findings that are generated by AWS security services, third\-party solutions, or Security Hub itself from running security checks\. For more information, see [AWS Security Finding Format \(ASFF\)](securityhub-findings-format.md)\.

**Control**  
A safeguard or countermeasure prescribed for an information system or an organization designed to protect the confidentiality, integrity, and availability of its information and to meet a set of defined security requirements\. A security standard consists of controls\.

**Custom action**  
A Security Hub mechanism for sending selected findings to CloudWatch Events\. A custom action is created in Security Hub\. It is then linked to a CloudWatch Events rule\. The rule defines a specific action to take when a finding is received that is associated with the custom action ID\. Custom actions can be used, for example, to send a specific finding, or a small set of findings, to a response or remediation workflow\. For more information, see [Creating a custom action and associating it with a CloudWatch Events rule](securityhub-cloudwatch-events.md#securityhub-cwe-configure)\.

**Finding**  
The observable record of a security check or security\-related detection\.  
For more information about findings in Security Hub, see [Findings in AWS Security Hub](securityhub-findings.md)\.  
Findings are deleted 90 days after the most recent update or 90 days after the creation date if no update occurs\. To store findings for longer than 90 days, you can configure a rule in CloudWatch Events that routes findings to your Amazon S3 bucket\.

**Insight**  
A collection of related findings defined by an aggregation statement and optional filters\. An insight identifies a security area that requires attention and intervention\. Security Hub offers several managed \(default\) insights that you can't modify\. You can also create custom Security Hub insights to track security issues that are unique to your AWS environment and usage\. For more information, see [Insights in AWS Security Hub](securityhub-insights.md)\.

**Related requirements**  
A set of industry or regulatory requirements that are mapped to a control\.

**Rule**  
A set of automated criteria that is used to assess whether a control is being adhered to\. When a rule is evaluated, it can pass or fail\. If the evaluation cannot determine whether rule passes or fails, then the rule is in a warning state\. If the rule cannot be evaluated, then it is in a not available state\.

**Security check**  
A specific point\-in\-time evaluation of a rule against a single resource resulting in a passed, failed, warning, or not available state\. Running a security check produces a finding\.

**Security standard**  
A published statement on a topic specifying the characteristics, usually measurable and in the form of controls, that must be satisfied or achieved for compliance\. Security standards can be based on regulatory frameworks, best practices, or internal company policies\. To learn more about security standards in Security Hub, see [Security standards in AWS Security Hub](securityhub-standards.md)\.