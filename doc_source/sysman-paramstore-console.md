# Walkthrough: Create and Use a Parameter in a Command \(Console\)<a name="sysman-paramstore-console"></a>

The following procedure walks you through the process of creating a parameter in Parameter Store and then running a command that uses this parameter\.

**To create a parameter using Parameter Store**

1. Open the AWS Systems Manager console at [https://console\.aws\.amazon\.com/systems\-manager/](https://console.aws.amazon.com/systems-manager/)\.

   \-or\-

   Open the Amazon EC2 console at [https://console\.aws\.amazon\.com/ec2/](https://console.aws.amazon.com/ec2/)\.
**Note**  
If you are using the Amazon EC2 console, some field names and locations may differ slightly\.

1. In the navigation pane, choose **Parameter Store**\. 

1. Choose **Create parameter**\.

1. In the **Name** box, enter a hierarchy and a name\. For example, enter **/Test/helloWorld**\.

   For more information about parameter hierarchies, see [Organizing Parameters into Hierarchies](sysman-paramstore-su-organize.md)\.

1. In the **Description** field, enter a description that identifies this parameter as a test parameter\.

1. For **Type**, choose **String**\.

1. In the **Value** field, enter a string\. For example, enter **My1stParameter**\.

1. Choose **Create parameter**\.

1. In the navigation pane, choose **Run Command**\. 

1. Choose **Run command**\.

1. In the **Command document** list, choose `AWS-RunPowershellScript` \(Windows\) or `AWS-RunShellScript` \(Linux\)\. 

1. Under **Target instances**, choose a managed instance in your account\.

1. In the **Commands** field, enter **echo \{\{ssm:*parameter\-name*\}\}**, for example, **echo \{\{ssm:/Test/helloWorld\}\}**\. 

1. Choose **Run**\.

1. Scroll to the bottom of the **Command ID** page, select the button next to an instance ID, and then choose **View output**\. 