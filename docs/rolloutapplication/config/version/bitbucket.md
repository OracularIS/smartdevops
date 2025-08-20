# Configure Bitbucket Integration

This page provides step-by-step guidance to configure git as your Version Control Provider.  

## Configuration Fields for Bitbucket

Below are the configuration fields and their values for setting up Azure as your version control provider:


<center>

| Field                        | Value              |
| ---------------------------- | --------------------------------- |
| Provider    | git                               |
| Provider Type| BitBucket                         |
| Base URI          | https://api.bitbucket.org         |
| API Version  | v2                               |
| Username     | Bitbucket account                 |
| Version Control Password  | PAT from Bitbucket                |
| WORKSPACE         | Your Bitbucket workspace name     |
| File Version                 | Latest                            |
| Default Branch              | your branch (e.g, main)                      |
| File Path   | your file path                  |


</center>

These values will be entered in the Version Control Provider settings form as shown in the example.

   <div style="text-align: left;">
      <img src="./assets/93.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

> 💡 **Tip:** Use the **suggestion button** to see recommended inputs and sample values for the field.  


## How to Generate Bitbucket PAT:

Follow the below mentioned steps to generate Bitbucket PAT:

1. Go to Account Settings 
2. Navigate to App Passwords
2. Create new token with all permissions

   <div style="text-align: left;">
      <img src="./assets/100.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. Use this token as your password

---
<br>