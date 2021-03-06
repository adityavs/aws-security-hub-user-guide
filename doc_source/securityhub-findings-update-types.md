# Types of finding updates in Security Hub<a name="securityhub-findings-update-types"></a>

In AWS Security Hub, a finding can originate from one of the following types of finding providers\.
+ An enabled integration with another AWS service
+ An enabled integration with a third\-party provider
+ An enabled security standard and control in Security Hub

After a finding is created, it can be updated by the finding provider or by the customer\.
+ The finding provider uses the [https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchImportFindings.html](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchImportFindings.html) API operation to update the general information about a finding\. Finding providers can only update findings that they created\.
+ The customer uses [https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchUpdateFindings.html](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchUpdateFindings.html) API operation to reflect the status of the investigation into a finding\. [https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchUpdateFindings.html](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchUpdateFindings.html) can also be used by a ticketing, incident management, orchestration, remediation, or SIEM tool on behalf of the customer\.

  From the Security Hub console, they can view finding details, manage the workflow status of findings, and send findings to custom actions\. See [Viewing and taking action on findings](securityhub-managing-findings.md)\.

**Topics**
+ [Using `BatchImportFindings` to create and update findings](finding-update-batchimportfindings.md)
+ [Using `BatchUpdateFindings` to update a finding](finding-update-batchupdatefindings.md)