# LDAP

![](../../../.gitbook/assets/graficos14%20%285%29.png)This category allows you to configure the synchronization with an LDAP server. It contains a long series of settings which all require a good knowledge of LDAP.

For more information, we invite you to follow LDAP-specific documentation. Note that an ActiveDirectory server can be used as an LDAP server through enabling its LDAP-compatibility mode.

The new LDAP plugin must be configured in main/inc/conf/auth.conf.php through the customization of the following section \(the in-line documentation for this plugin is wrong up to Chamilo 1.9.4\):

$extldap\_config = array\(

//base dommain string

'base\_dn' =&gt; 'DC=cblue,DC=be',

//admin distinguished name

'admin\_dn' =&gt; 'CN=admin,dc=cblue,dc=be',

//admin password

'admin\_password' =&gt; 'pass',

//ldap host

'host' =&gt; array\('1.2.3.4', '2.3.4.5', '3.4.5.6'\),

// filter

// 'filter' =&gt; '', // no \(\) arround the string

//'port' =&gt; , default on 389

//protocl version \(2 or 3\)

'protocol\_version' =&gt; 3,

// set this to 0 to connect to AD server

'referrals' =&gt; 0,

//String used to search the user in ldap. %username will ber replaced by the username.

//See extldap\_get\_user\_search\_string\(\) function below

// 'user\_search' =&gt; 'sAMAccountName=%username%', // no \(\) arround the string

'user\_search' =&gt; 'uid=%username%', // no \(\) arround the string

//encoding used in ldap \(most common are UTF-8 and ISO-8859-1

'encoding' =&gt; 'UTF-8',

//Set to true if user info have to be update at each login

'update\_userinfo' =&gt; true

\);
