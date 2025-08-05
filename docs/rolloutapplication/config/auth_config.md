# AUTH Configuration

This section allows you to enable or disable the different authentication mechanisms:

- **AUTH Database Configuration**: Enables authentication using credentials stored in a local database.
- **AUTH LDAP Configuration**: Enables authentication using LDAP (Lightweight Directory Access Protocol).
- **Login With Azure Configuration**: Enables Microsoft Azure Active Directory login.
- **Login With Google Configuration**: Enables Google OAuth2 login.

  <div style="text-align: left;">
      <img src="./assets/auth.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

## AUTH Database Configuration

Used when AUTH Database Configuration is enabled.

- **SUPER_USER**: This is the default administrator username for the system when using database-based login.


### Login With Azure Configuration

Used when Login with Azure Configuration is enabled.

- **AZURE_CLIENT_ID**: The Client ID obtained from Azure Active Directory for your application.
- **AZURE_CLIENT_SECRET**: The secret key associated with the Azure Client ID.
- **AZURE_TENANT_ID**: The Azure Directory (tenant) ID for your organization.
- **AZURE_REDIRECT_URI**: The URI Azure will redirect users to after a successful login.

**Example:**

```
http://localhost:8081/social/login/callback
```

> Make sure this URI matches the one registered in your Azure AD application.

---

### Login With Google Configuration

Used when Login With Google Configuration is enabled.

- **GOOGLE_CLIENT_ID**: The Client ID obtained from Google Cloud Console for your application.
- **GOOGLE_CLIENT_SECRET**: The secret key associated with the Google Client ID.
- **GOOGLE_REDIRECT_URL**: The URI Google will redirect users to after successful login.

**Example:**

```
http://localhost:8081/social/login/callback
```
---
<br>