# Best practices<a name="channels-sms-best-practices"></a>

Mobile phone users tend to have a very low tolerance for unsolicited SMS messages\. Response rates for unsolicited SMS campaigns will almost always be low, and therefore the return on your investment will be poor\.

Additionally, mobile phone carriers continuously audit bulk SMS senders\. They throttle or block messages from numbers that they determine to be sending unsolicited messages\. 

Sending unsolicited content is also a violation of the [AWS acceptable use policy](https://aws.amazon.com/aup/#No_E-Mail_or_Other_Message_Abuse)\. The Amazon Pinpoint team routinely audits SMS campaigns, and might throttle or block your ability to send messages if it appears that you're sending unsolicited messages\.

Finally, in many countries, regions, and jurisdictions, there are severe penalties for sending unsolicited SMS messages\. For example, in the United States, the Telephone Consumer Protection Act \(TCPA\) states that consumers are entitled to $500–$1,500 in damages \(paid by the sender\) for each unsolicited message that they receive\.

This section describes several best practices that might help you improve your customer engagement and avoid costly penalties\. However, note that this section doesn't contain legal advice\. Always consult an attorney to obtain legal advice\.

**Topics**
+ [Comply with laws, regulations, and carrier requirements](#channels-sms-best-practices-understand-laws)
+ [Obtain permission](#channels-sms-best-practices-obtain-permission)
+ [Don't send to old lists](#channels-sms-best-practices-old-lists)
+ [Audit your customer lists](#channels-sms-best-practices-audit-lists)
+ [Keep records](#channels-sms-best-practices-keep-records)
+ [Make your messages clear, honest, and concise](#channels-sms-best-practices-appropriate-content)
+ [Respond appropriately](#channels-sms-best-practices-respond-appropriately)
+ [Adjust your sending based on engagement](#channels-sms-best-practices-adjust-engagement)
+ [Send at appropriate times](#channels-sms-best-practices-appropriate-times)
+ [Avoid cross\-channel fatigue](#channels-sms-best-practices-cross-channel-fatigue)
+ [Use dedicated short codes](#channels-sms-best-practices-dedicated-short-codes)
+ [Verify your destination phone numbers](#channels-sms-best-practices-verify-destination-numbers)
+ [Design with redundancy in mind](#channels-sms-best-practices-redundancy)

## Comply with laws, regulations, and carrier requirements<a name="channels-sms-best-practices-understand-laws"></a>

You can face significant fines and penalties if you violate the laws and regulations of the places where your customers reside\. For this reason, it's vital to understand the laws related to SMS messaging in each country or region where you do business\.

The following list includes links to key laws that apply to SMS communications in major markets around the world\.
+ **United States**: The Telephone Consumer Protection Act of 1991, also known as TCPA, applies to certain types of SMS messages\. For more information, see the [rules and regulations](https://www.fcc.gov/document/telephone-consumer-protection-act-1991) at the Federal Communications Commission website\.
+ **United Kingdom**: The Privacy and Electronic Communications \(EC Directive\) Regulations 2003, also known as PECR, applies to certain types of SMS messages\. For more information, see [What are PECR?](https://ico.org.uk/for-organisations/guide-to-pecr/what-are-pecr/) at the website of the UK Information Commissioner's Office\.
+ **European Union**: The Privacy and Electronic Communications Directive 2002, sometimes known as the ePrivacy Directive, applies to some types of SMS messages\. For more information, see the [full text of the law](http://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32002L0058) at the Europa\.eu website\.
+ **Canada**: The Fighting Internet and Wireless Spam Act, more commonly known as Canada's Anti\-Spam Law or CASL, applies to certain types of SMS messages\. For more information, see the [full text of the law](http://www.parl.ca/DocumentViewer/en/40-3/bill/C-28/first-reading) at the website of the Parliament of Canada\.
+ **Japan**: The Act on Regulation of Transmission of Specific Electronic Mail may apply to certain types of SMS messages\. For more information, see [Japan's countermeasures against spam](http://measures.antispam.soumu.go.jp/) at the website of the Japanese Ministry of Internal Affairs and Communications\.

As a sender, these laws may apply to you even if your company or organization isn't based in one of these countries\. Some of the laws in this list were originally created to address unsolicited email or telephone calls, but have been interpreted or expanded to apply to SMS messages as well\. Other countries and regions may have their own laws related to the transmission of SMS messages\. Consult an attorney in each country or region where your customers are located to obtain legal advice\.

In many countries, the local carriers ultimately have the authority to determine what kind of traffic flows over their networks\. This means that the carriers might impose restrictions on SMS content that exceed the minimum requirements of local laws\.

## Obtain permission<a name="channels-sms-best-practices-obtain-permission"></a>

Never send messages to customers who haven't explicitly asked to receive the specific types of messages that you plan to send\. Don't share opt\-in lists, even among organizations within the same company\. 

If customers can sign up to receive your messages by using an online form, add systems that prevent automated scripts from subscribing people without their knowledge\. You should also limit the number of times a user can submit a phone number in a single session\.

When you receive an SMS opt\-in request, send the customer a message that asks them to confirm that they want to receive messages from you\. Don't send that customer any additional messages until they confirm their subscription\. A subscription confirmation message might resemble the following example:

`Text YES to join ExampleCorp alerts. 2 msgs/month. Msg & data rates may apply. Reply HELP for help, STOP to cancel.`

Maintain records that include the date, time, and source of each opt\-in request and confirmation\. This might be useful if a carrier or regulatory agency requests it, and can also help you perform routine audits of your customer list\.

Finally, note that transactional SMS messages, such as order confirmations or one\-time passwords, typically don't require explicit consent as long as you tell your customers that you're going to send them these messages\. However, you should never send marketing messages to customers who only provided you with permission to send them transactional messages\.

## Don't send to old lists<a name="channels-sms-best-practices-old-lists"></a>

People change phone numbers often\. A phone number that you gathered consent to contact two years ago might belong to somebody else today\. Don't use an old list of phone numbers for a new messaging program; if you do, you're likely to have some messages fail because the number is no longer in service, and some people who opt out because they don't remember giving you their consent in the first place\.

## Audit your customer lists<a name="channels-sms-best-practices-audit-lists"></a>

If you send recurring SMS campaigns, audit your customer lists on a regular basis\. Auditing your customer lists ensures that the only customers who receive your messages are those who are interested in receiving them\. 

When you audit your list, send each opted\-in customer a message that reminds them that they're subscribed, and provides them with information about unsubscribing\. A reminder message might resemble the following example:

`You're subscribed to ExampleCorp alerts. Msg & data rates may apply. Reply HELP for help, STOP to unsubscribe.`

## Keep records<a name="channels-sms-best-practices-keep-records"></a>

Keep records that show when each customer requested to receive SMS messages from you, and which messages you sent to each customer\. Many countries and regions around the world require SMS senders to maintain these records in a way that can be easily retrieved\. Mobile carriers might also request this information from you at any time\. The exact information that you have to provide varies by country or region\. For more information about record\-keeping requirements, review the regulations about commercial SMS messaging in each country or region where your customers are located\.

Occasionally, a carrier or regulatory agency asks us to provide proof that a customer opted to receive messages from you\. In these situations, AWS Support contacts you with a list of the information that the carrier or agency requires\. If you can't provide the necessary information, we may pause your ability to send additional SMS messages\.

## Make your messages clear, honest, and concise<a name="channels-sms-best-practices-appropriate-content"></a>

SMS is a unique medium\. The 160\-character\-per\-message limit means that your messages have to be concise\. Techniques that you might use in other communication channels, such as email, might not apply to the SMS channel, and might even seem dishonest or deceptive when used with SMS messages\. If the content in your messages doesn't align with best practices, recipients might ignore your messages; in the worst case, the mobile carriers might identify your messages as spam and block future messages from your phone number\.

This section provides some tips and ideas for creating an effective SMS message body\.

### Identify yourself as the sender<a name="channels-sms-best-practices-appropriate-content-identify"></a>

Your recipients should be able to immediately tell that a message is from you\. Senders who follow this best practice include an identifying name \("program name"\) at the beginning of each message\.

**Don't do this:**  
`Your account has been accessed from a new device. Reply Y to confirm.`

**Try this instead:**  
`ExampleCorp Financial Alerts: You have logged in to your account from a new device. Reply Y to confirm, or STOP to opt-out.`

### Don't try to make your message look like a person\-to\-person message<a name="channels-sms-best-practices-appropriate-content-p2p"></a>

Some marketers are tempted to add a personal touch to their SMS messages by making their messages appear to come from an individual\. However, this technique might make your message seem like a phishing attempt\.

**Don't do this:**  
`Hi, this is Jane. Did you know that you can save up to 50% at Example.com? Click here for more info: https://www.example.com.`

**Try this instead:**  
`ExampleCorp Offers: Save 25-50% on sale items at Example.com. Click here to browse the sale: https://www.example.com. Text STOP to opt-out.`

### Be careful when talking about money<a name="channels-sms-best-practices-appropriate-content-money"></a>

Scammers often prey upon people's desire to save and receive money\. Don't make offers seem too good to be true\. Don't use the lure of money to deceive people\. Don't use currency symbols to indicate money\.

**Don't do this:**  
`Save big $$$ on your next car repair by going to https://www.example.com.`

**Try this instead:**  
`ExampleCorp Offers: Your ExampleCorp insurance policy gets you discounts at 2300+ repair shops nationwide. More info at https://www.example.com. Text STOP to opt-out.`

### Use only the necessary characters<a name="channels-sms-best-practices-appropriate-content-characters"></a>

Brands are often inclined to protect their trademarks by including trademark symbols such as ™ or ® in their messages\. However, these symbols are not part of the standard set of characters \(known as the GSM alphabet\) that can be included in a 160\-character SMS message\. When you send a message that contains one of these characters, your message is automatically sent using a different character encoding system, which only supports 70 characters per message part\. As a result, your message could be broken into several parts\. Because you're billed for each message part that you send, it could cost you more than you expect to spend to send the entire message\. Additionally, your recipients might receive several sequential messages from you, rather than one single message\. For more information about SMS character encoding, see [SMS character limits in Amazon Pinpoint](channels-sms-limitations-characters.md)\.

**Don't do this:**  
`ExampleCorp Alerts: Save 20% when you buy a new ExampleCorp Widget® at example.com and use the promo code WIDGET.`

**Try this instead:**  
`ExampleCorp Alerts: Save 20% when you buy a new ExampleCorp Widget(R) at example.com and use the promo code WIDGET.`

**Note**  
The two preceding examples are almost identical, but the first example contains a Registered Trademark symbol \(®\), which is not part of the GSM alphabet\. As a result, the first example is sent as two message parts, while the second example is sent as one message part\.

### Use valid, safe links<a name="channels-sms-best-practices-appropriate-content-links"></a>

If your message includes links, double\-check the links to make sure that they work\. Test your links on a device outside your corporate network to ensure that links resolve properly\. Because of the 160\-character limit of SMS messages, very long URLs could be split across multiple messages\. You should use redirect domains to provide shortened URLs\. However, you shouldn't use free link\-shortening services such as tinyurl\.com or bitly\.com, because carriers tend to filter messages that include links on these domains\. However, you can use paid link\-shortening services as long as your links point to a domain that is dedicated to the exclusive use of your company or organization\. 

**Don't do this:**  
`Go to https://tinyurl.com/4585y8mr today for a special offer!`

**Try this instead:**  
`ExampleCorp Offers: Today only, get an exclusive deal on an ExampleCorp Widget. See https://a.co/cFKmaRG for more info. Text STOP to opt-out.`

### Limit the number of abbreviations that you use<a name="channels-sms-best-practices-appropriate-content-abbrev"></a>

The 160\-character limitation of the SMS channel leads some senders to believe that they need to use abbreviations extensively in their messages\. However, the overuse of abbreviations can seem unprofessional to many readers, and could cause some users to report your message as spam\. It's completely possible to write a coherent message without using an excessive number of abbreviations\.

**Don't do this:**  
`Get a gr8 deal on ExampleCorp widgets when u buy a 4-pack 2day.`

**Try this instead:**  
`ExampleCorp Alerts: Today only—an exclusive deal on ExampleCorp Widgets at example.com. Text STOP to opt-out.`

## Respond appropriately<a name="channels-sms-best-practices-respond-appropriately"></a>

When a recipient replies to your messages, make sure that you respond with useful information\. For example, when a customer responds to one of your messages with the keyword "HELP", send them information about the program that they're subscribed to, the number of messages you'll send each month, and the ways that they can contact you for more information\. A HELP response might resemble the following example:

`HELP: ExampleCorp alerts: email help@example.com or call 425-555-0199. 2 msgs/month. Msg & data rates may apply. Reply STOP to cancel.`

When a customer replies with the keyword "STOP", let them know that they won't receive any further messages\. A STOP response might resemble the following example:

`You're unsubscribed from ExampleCorp alerts. No more messages will be sent. Reply HELP, email help@example.com, or call 425-555-0199 for more info.`

## Adjust your sending based on engagement<a name="channels-sms-best-practices-adjust-engagement"></a>

Your customers' priorities can change over time\. If customers no longer find your messages to be useful, they might opt out of your messages entirely, or even report your messages as unsolicited\. For these reasons, it's important that you adjust your sending practices based on customer engagement\.

For customers who rarely engage with your messages, you should adjust the frequency of your messages\. For example, if you send weekly messages to engaged customers, you could create a separate monthly digest for customers who are less engaged\. 

Finally, remove customers who are completely unengaged from your customer lists\. This step prevents customers from becoming frustrated with your messages\. It also saves you money and helps protect your reputation as a sender\.

## Send at appropriate times<a name="channels-sms-best-practices-appropriate-times"></a>

Only send messages during normal daytime business hours\. If you send messages at dinner time or in the middle of the night, there's a good chance that your customers will unsubscribe from your lists in order to avoid being disturbed\. Furthermore, it doesn't make sense to send SMS messages when your customers can't respond to them immediately\. 

If you send campaigns or journeys to very large audiences, double\-check the throughput rates for your origination numbers\. Divide the number of recipients by your throughput rate to determine how long it will take to send messages to all of your recipients\.

## Avoid cross\-channel fatigue<a name="channels-sms-best-practices-cross-channel-fatigue"></a>

In your campaigns, if you use multiple communication channels \(such as email, SMS, and push messages\), don't send the same message in every channel\. When you send the same message at the same time in more than one channel, your customers will probably perceive your sending behavior to be annoying rather than helpful\.

## Use dedicated short codes<a name="channels-sms-best-practices-dedicated-short-codes"></a>

If you use short codes, maintain a separate short code for each brand and each type of message\. For example, if your company has two brands, use a separate short code for each one\. Similarly, if you send both transactional and promotional messages, use a separate short code for each type of message\. To learn more about requesting short codes, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\.

## Verify your destination phone numbers<a name="channels-sms-best-practices-verify-destination-numbers"></a>

When you send SMS messages through Amazon Pinpoint, you're billed for each message part you send\. The price you pay per message part varies on the recipient's country or region\. For more information about SMS pricing, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/#SMS_text_messages)\.

When Amazon Pinpoint accepts a request to send an SMS message \(as the result of a call to the [SendMessages](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-messages.html#SendMessages) API, or as the result of a campaign or journey being launched\), you're charged for sending that message\. This statement is true even if the intended recipient doesn't actually receive the message\. For example, if the recipient's phone number is no longer in service, or if the number that you sent the message to wasn't a valid mobile phone number, you're still billed for sending the message\.

Amazon Pinpoint accepts valid requests to send SMS messages and attempts to deliver them\. For this reason, you should validate that the phone numbers that you send messages to are valid mobile numbers\. You can use the Amazon Pinpoint phone number validation service to determine if a phone number is valid and what type of number it is \(such as mobile, landline, or VoIP\)\. For more information, see [Validating phone numbers in Amazon Pinpoint](https://docs.aws.amazon.com/pinpoint/latest/developerguide/validate-phone-numbers.html) in the *Amazon Pinpoint Developer Guide*\.

## Design with redundancy in mind<a name="channels-sms-best-practices-redundancy"></a>

For mission\-critical messaging programs, we recommend that you configure Amazon Pinpoint in more than one AWS Region\. Amazon Pinpoint is available in several AWS Regions\. For a complete list of Regions where Amazon Pinpoint is available, see the [AWS General Reference](https://docs.aws.amazon.com/general/latest/gr/pinpoint.html)\. 

The phone numbers that you use for SMS messages—including short codes, long codes, toll\-free numbers, and 10DLC numbers—can't be replicated across AWS Regions\. As a result, in order to use Amazon Pinpoint in multiple Regions, you must request separate phone numbers in each Region where you want to use Amazon Pinpoint\. For example, if you use a short code to send text messages to recipients in the United States, you need to request separate short codes in each AWS Region that you plan to use\.

In some countries, you can also use multiple types of phone numbers for added redundancy\. For example, in the United States, you can request short codes, 10DLC numbers, and toll\-free numbers\. Each of these phone number types takes a different route to the recipient\. Having multiple phone number types available—either in the same AWS Region or spread across multiple AWS Regions—provides an additional layer of redundancy, which can help improve resiliency\.