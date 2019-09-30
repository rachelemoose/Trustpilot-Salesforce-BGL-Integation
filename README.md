# Trustpilot-Salesforce-BGL-Integation
Trustpilot integration with Salesforce for Trustpilot's product [Business Generated Links](https://support.trustpilot.com/hc/en-us/articles/115004145087--Business-Generated-Links-for-developers-)

This integation uses [Python Simple-Salesforce package](https://pypi.org/project/simple-salesforce/). 

# Installation 
pip install simple-salesforce (https://pypi.org/project/simple-salesforce/)

## Authentication and Customization
**Salesforce Authentication**
- username = your Salesforce username used to login 
- password = your Salesforce password used to login
- security_token = your Salesforce account security token - can be reset following [these instructions](https://onlinehelp.coveo.com/en/ces/7.0/administrator/getting_the_security_token_for_your_salesforce_account.htm)

**Trustpilot Authentication (BGL Keys)**
Use the encryption key and the authentication key provided by Trustpilot. You can find these in your account under "Get Reviews". 

# Encryption
Customer data will be pulled from Salesforce in a JSON format, specifically email, name, and a unique reference number. We are using Salesforce's uniqueID but you can use any unique value for the customer. 

Example:
```{

"email":"xyz@domain.com",

"name":"John Smith",

"ref":"1234",

"skus":["sku1","sku2","sku3"],

"tags":["tag1","tag2","tag3"]

}


The encryption process will run without any customization needed. The final link will be printed in the command line for reference, then stored back into Salesforce in the "description" field. You can customize this so that the Business Generated Link is stored in any Salesforce field. 
