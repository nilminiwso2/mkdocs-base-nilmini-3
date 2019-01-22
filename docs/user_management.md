# User Management
User management configurations define how the WSO2 product is configured to store, manage, and control details about users that access the product. 
To configure user management for your product, add the sections listed below (headings and parameters) to the .toml file. 

## **[user_mgt]**

The section groups the general configurations related to user management, such as the default user roles, etc.

**Parameters (Required)**

| Parameter      | Description  | 
| ------------- |-------------| 
| role_to_assign_by_default     | Role name that will get assigned to all new users created in the system. For example ```-role_to_assign_by_default="everyone"```  | 
| properties     | Custom datasource properties if required      |  

**Parameters (Optional)**

| Parameter      | Description  | 
| ------------- |-------------| 
| authorization_mgt.properties     | Description of this property | 

## **[user_mgt.userstore]**

**Parameters (Required)**

| Parameter      | Description  | 
| ------------- |-------------| 
| user_identifier_attribute    | Role name that will get assigned for all the users created | 
| type     | The type of data store that is used as the user store. The possible values are as follows:      | 

**User Store Properties (Required) - Read/Write LDAP**


| Parameter      | Description  | 
| ------------- |-------------| 
| read_write_ldap.connection_url     | Connection URL to the user store server. In the case of default LDAP in Carbon, the port is specified in the carbon.xml file, and a reference to that port is included in this configuration. **Example:** ```-read_write_ldap.connection_url="ldap://localhost:${Ports.EmbeddedLDAP.LDAPServerPort}"```| 
| read_write_ldap.connection_name     | The username used to connect to the database and perform various operations. This user does not have to be an administrator in the user store or have an administrator role in the WSO2 product that you are using, but this user MUST have permissions to read the user list and users' attributes and to perform search operations on the user store. The value you specify is used as the DN (Distinguish Name) attribute of the user. This property is mandatory. **Example:** ```-read_write_ldap.connection_name="uid=admin,ou=system"``` | 
| read_write_ldap.connection_password     | Password for the ConnectionName user. **Example:** ```-read_write_ldap.connection_password="admin"```| 
| read_write_ldap.user_search_base     | DN of the context or object under which the user entries are stored in the user store. In this case, it is the "users" container. When the user store searches for users, it will start from this location of the directory. **Example:** ```-read_write_ldap.user_search_base="ou=Users,dc=wso2,dc=org"``` | 

**User Store Properties (Optional) - Read/Write LDAP**

| Parameter      | Description  | 
| ------------- |-------------| 
| read_write_ldap.connection_url     | Description of this property | 
| read_write_ldap.connection_name     | Description of this property | 
| read_write_ldap.connection_password     | Description of this property | 
| read_write_ldap.user_search_base     | Description of this property | 