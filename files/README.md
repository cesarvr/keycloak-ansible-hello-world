## Keycloak Configuration Resource

Here find the minimum configuration template for some of the Keycloak resources. 


- **User**

    **Resource Name:** ``users``
    ```js
      {"enabled":true,"attributes":{},"username":"batman","firstName":"Bruce", "lastName":"Wayne", "emailVerified":""}
    ```

    For more information on the [user API](https://access.redhat.com/webassets/avalon/d/red-hat-single-sign-on/version-7.0.0/restapi/#_userrepresentation).

- **Client**

    **Resource Name:** ``clients``

    ```js
    {"enabled":true,"attributes":{},"redirectUris":[],"clientId":"dc","protocol":"openid-connect"}
    ```
    For more information on the [client API](
    https://access.redhat.com/webassets/avalon/d/red-hat-single-sign-on/version-7.0.0/restapi/#_clientrepresentation).


    > Although client API is very robust and it can be used to register SAML/OpenID client is recommeded to use the [OpenID client registration endpoint](https://openid.net/specs/openid-connect-registration-1_0.html) for this purposes as it provide a more standard implementation.


- **Components**
  
  - **Realm Keys**
  
    In the case you need to configure realm keys. 

    **Resource Name:** ``components``

    ```js
    {
        "config": {
            "active": [
                "true"
            ],
            "algorithm": [
                "RS256"
            ],
            "enabled": [
                "true"
            ],
            "keySize": [
                "2048"
            ],
            "priority": [
                "0"
            ]
        },
        "name": "rsa-generated-for-heroes",
        "providerId": "rsa-generated",
        "providerType": "org.keycloak.keys.KeyProvider"
    }
    ```

   - **Federation Plugin**
   
     If you want to source users from third party this is the type of configuration you need to use.  

     **Resource Name:** ``components``

      Example below for a Kerberos configuration: 

      ```js
      {
          "config": {
              "allowPasswordAuthentication": [
                  "false"
              ],
              "cachePolicy": [
                  "DEFAULT"
              ],
              "debug": [
                  "false"
              ],
              "editMode": [],
              "enabled": [
                  "false"
              ],
              "evictionDay": [],
              "evictionHour": [],
              "evictionMinute": [],
              "kerberosRealm": [
                  "FOO.ORG"
              ],
              "keyTab": [
                  "/etc/keytab"
              ],
              "maxLifespan": [],
              "priority": [
                  "0"
              ],
              "serverPrincipal": [
                  "HTTP/foo"
              ],
              "updateProfileFirstLogin": [
                  "false"
              ]
          },
          "name": "kerberos-atlas-1",
          "parentId": "heroes",
          "providerId": "kerberos",
          "providerType": "org.keycloak.storage.UserStorageProvider"
      }
      ```


