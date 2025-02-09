# Managing SMS and voice settings in Amazon Pinpoint<a name="settings-sms-managing"></a>

Within your Amazon Pinpoint account, you can change several settings that determine how your messages in the SMS and voice channels behave\. This section provides information about these settings, and procedures for changing them\.

**Topics**
+ [Changing SMS settings](#settings-account-sms-managing)
+ [Managing number settings](#settings-account-sms-number)
+ [Removing a number](#settings-account-sms-remove)

## Changing SMS settings<a name="settings-account-sms-managing"></a>

The Amazon Pinpoint console provides several options to help you update and manage SMS channel settings to match your use case and budget\. For example, you can enable or disable the SMS channel for a specific project, set a monthly SMS spending quota for your AWS account, or change the default message type for your AWS account\.

**To change SMS settings**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, do one of the following:
   + To change SMS settings for a specific project, choose the project\.
   + To change SMS settings for your AWS account, choose any project\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. On the **SMS and voice** settings page, next to **General**, choose **Edit**\.

1. On the **Edit SMS** page, change any of the following settings:
   + **Enable the SMS channel for this project** – Select this option to enable the SMS channel for the current project\. To disable the SMS channel for the project, clear this option\.
   + **Account\-level settings** – Change these settings to modify the SMS settings for your AWS account\. These settings apply to your entire Amazon Pinpoint account and to all AWS services that you can use to send SMS messages, such as Amazon Simple Notification Service\. You can change the following settings:
     + **Default message type** – Choose the type of SMS messages that you plan to send\. If you plan to send time\-sensitive content, such as alerts and one\-time passwords, choose **Transactional**\. If you plan to send marketing\-related content, choose **Promotional**\.
     + **Account spending limit** – Specify the maximum amount of money, in US Dollars, that you want to spend sending SMS messages during each calendar month\.
     + **Default sender ID** – Optionally, specify the sender ID that you plan to use to send SMS messages\. A sender ID is an alphanumeric identifier that appears on recipients' devices when they receive messages from you\. Support for sender IDs varies by country or region\. For more information, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.

1. When you finish making changes, choose **Save changes**\.

## Managing number settings<a name="settings-account-sms-number"></a>

You can use the options in the **Number settings** section of the **SMS and voice** settings page to manage settings for the dedicated *short codes* and *long codes* that you requested from AWS Support and assigned to your account\. A short code is a five\-digit or six\-digit number that's meant for high\-volume SMS messaging\. To learn how to request a dedicated short code, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\. A long code is a standard 10\-digit phone number that's meant for low\-volume, person\-to\-person communication\. To learn how to request a dedicated long code, see [Requesting dedicated long codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\.

After you receive one or more dedicated short codes or long codes from AWS Support, those numbers appear in the **Number settings** section, where you can manage SMS keyword settings and two\-way SMS messaging settings for the numbers\.

### Keyword settings<a name="settings-account-sms-number-keyword"></a>

A *keyword* is a specific word or phrase that a customer can send to your number to elicit a response, such as an informational message or a special offer\. When your number receives a message that begins with a keyword, Amazon Pinpoint responds with a customizable message\.

For short codes, the console shows the keywords and responses that you initially define when you request a short code from AWS Support\. AWS Support registers your keywords and responses with wireless carriers when it provisions your short code\.

For long codes, the console shows the default keywords and responses\.

**Important**  
Your keywords and response messages must comply with the guidelines that are set by wireless carriers and wireless industry groups\. Otherwise, following an audit, such groups might take action against your short code or long code\. This action can include deny listing your number and blocking your messages\.

#### Default keywords<a name="settings-account-sms-number-keyword-default"></a>

Wireless carriers in the US require short codes to support the following keywords\. In addition, AWS expects all long codes and short codes to support these keywords:

HELP  
Used to obtain customer support\. The response message must include customer\-support contact information, as in the following example:  
*"For assistance with your account, call \(206\) 555\-0199\."*

STOP  
Used to opt out of receiving messages from your number\. In addition to *STOP*, your audience can use any supported opt\-out keyword, such as *CANCEL* or *OPTOUT*\. For a list of supported opt\-out keywords, see [SMS opt out](channels-sms-manage.md#channels-sms-manage-optout)\. After your number receives an SMS message that contains an opt\-out keyword, Amazon Pinpoint stops sending SMS messages from your account to the individual who opted out\.  
The response message must confirm that messages will stop being sent to the individual who opted out, as in the following example:  
*"You are now opted out and will no longer receive messages\."*

**Note**  
If a recipient responds with one of these keywords as the first word of their message, Amazon Pinpoint responds with the response for that keyword\. For example, if a recipient responds to one of your messages with "Help me understand what this means," then Amazon Pinpoint responds with the response that you specified for the HELP keyword\.

#### Registered keyword<a name="settings-account-sms-number-keyword-registered"></a>

A *registered keyword* is a keyword that's specific to your SMS use case\. When you use short codes, you're required to register this keyword with wireless carriers\. Customers can send this keyword to your short code to get more information about the products and services that you offer\.

#### Changing keyword settings<a name="settings-account-sms-number-keyword-managing"></a>

Use the Amazon Pinpoint console to customize the keyword responses for your number\.

**Important**  
Required opt\-out and opt\-in keyword responses for US toll\-free numbers are STOP and UNSTOP, which are managed by carriers\. When a user replies to your message with STOP or UNSTOP, the carrier sends the response message\. On the Amazon Pinpoint console these fields are unavailable\.

1. On the **SMS and voice** settings page, under **Number settings**, choose the short code or long code that you want to manage keyword responses for\.

   Under **Keywords**, the console provides options for:
   + The default *HELP* and *STOP* keywords\. You can edit the response messages, but you can't edit the keywords\.
   + Your registered keyword\. If you want to change your registered keyword, you need to first open a case with AWS Support and request to update the keyword with wireless carriers\. Then, you need to edit the keyword in the Amazon Pinpoint console to match\. You can also edit the response message, but the intent of the message must remain consistent with the message that you provide to AWS Support\.

1. In the table that contains the keyword that you want to edit, choose **Edit**, and then edit the keyword and response message\.

1. When you finish making changes, choose **Save**\.

### Two\-way SMS settings<a name="settings-account-sms-number-2way"></a>

You can configure Amazon Pinpoint to handle incoming SMS messages\. When your number receives an SMS message, Amazon Pinpoint sends the message and related data to an Amazon Simple Notification Service \(Amazon SNS\) topic\. You can then use Amazon SNS to publish the message to topic subscribers or to AWS services for further processing\.

For more information about setting up two\-way messaging, see [Configuring two\-way SMS messaging in Amazon Pinpoint](channels-sms-two-way.md)\.

### Self\-managed opt\-outs<a name="settings-account-sms-self-managed-opt-out"></a>

By default, when a customer sends a message that begins with *HELP* or *STOP* to one of your dedicated numbers, Amazon Pinpoint automatically replies with a customizable message\. In the case of incoming STOP messages, Amazon Pinpoint also opts the customer out of receiving future SMS messages\. If you prefer to manage HELP and STOP responses by using a service other than Amazon Pinpoint, you can enable self\-managed opt\-outs\. 

**Note**  
To enable self\-managed opt\-outs for a number, you must first enable two\-way SMS messaging for that number\.

When you enable this feature, there are three changes to the way that Amazon Pinpoint handles incoming messages that your customers send to the specified long or short code\. First, it stops sending automatic responses to incoming HELP and STOP messages\. \(However, you can use [keyword settings](#settings-account-sms-number-keyword-managing) to manually configure responses to these messages\.\) Second, Amazon Pinpoint stops automatically opting your customers out of receiving future SMS messages when they send a STOP message\. And finally, it routes incoming HELP and STOP messages to the Amazon SNS topic that you use to receive two\-way SMS messages, rather than responding to the sender automatically\. 

If you enable this feature, you're responsible for responding to HELP and STOP requests\. You're also responsible for tracking and honoring opt\-out requests\.

**Important**  
Many countries, regions, and jurisdictions impose severe penalties for sending unwanted SMS messages\. If you enable this feature, make sure you have systems and processes in place for capturing and managing opt\-out requests\.

**To enable self\-managed opt\-outs**

1. Under **Number settings**, choose the short code or long code that you want to enable self\-managed opt\-outs for\.

1. On the **Number settings** page, choose **Two\-way SMS**\.

1. Enable and set up two\-way SMS messaging, if you haven't already done so\. For information about setting up two\-way SMS messaging, see [Configuring two\-way SMS messaging in Amazon Pinpoint](channels-sms-two-way.md)\. 

1. Under **Opt\-outs**, choose **Enable self\-managed opt\-outs**\.

## Removing a number<a name="settings-account-sms-remove"></a>

If you don't need a dedicated phone number anymore, you can remove it from your account\. When you remove a number, we stop charging you for it in your bill for the next calendar month\.

**Important**  
Removing a phone number from your account is permanent and can't be undone\. If you remove a phone number, you won't be able to obtain the same number again in the future\.

**To remove a number from your account**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. In the **Number settings** section, choose the phone number that you want to remove\. Choose **Remove phone number**\.
**Note**  
You can only remove one number at a time\.

1. On the **Remove number confirmation** window, enter **delete** in the text field, and then choose **Delete**\.