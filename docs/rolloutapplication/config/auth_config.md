# AUTH Configuration

This section allows you to enable or disable the different authentication mechanisms:

- **AUTH Database Configuration**: Enables authentication using credentials stored in a local database.
- **AUTH LDAP Configuration**: Enables authentication using LDAP (Lightweight Directory Access Protocol).
- **Login With Azure Configuration**: Enables Microsoft Azure Active Directory login.
- **Login With Google Configuration**: Enables Google OAuth2 login.

  <div style="text-align: left;">
      <img src="./assets/96.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

## AUTH Database Configuration

This configuration is used when AUTH Database Configuration is enabled.

<center>

| Field        | Value                                                                    |
|--------------|---------------------------------------------------------------------------------|
| SUPER USER | default administrator username e.g, `admin` |

</center>


  <div style="text-align: left;">
      <img src="./assets/97.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


## Login With Azure Configuration

This configuration is used when Login with Azure Configuration is enabled.


<center>

| Field                  | Description                                                                                     |
|------------------------|-------------------------------------------------------------------------------------------------|
| Azure Cient ID   | The Client ID obtained from Azure Active Directory for your application.                        |
| Azure Client Secret| The secret key associated with the Azure Client ID.                                             |
| Azure Tenant ID    | The Azure Directory (tenant) ID for your organization.                                          |
| Azure Redirect URI | https://yourapp.com/auth/azure/callback  |

  <div style="text-align: left;">
      <img src="./assets/99.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


</center>
> Make sure this URI matches the one registered in your Azure AD application.


## Login With Google Configuration

This configuration is used  when Login With Google Configuration is enabled.


<center>

| Field                  | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| Google Client ID     | The Client ID obtained from Google Cloud Console for your application.     |
| Google Client Secret| The secret key associated with the Google Client ID.                       |
| Google Redirect URL  |https://yourapp.com/auth/google/callback            |


</center>

  <div style="text-align: left;">
      <img src="./assets/98.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

> 💡 **Tip:** Use the **suggestion button** to see recommended inputs and sample values for the field.  

---
<br>