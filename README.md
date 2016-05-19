limesurvey-saml  (version 0.1)
==============================

SAML Authentication plugin for limesurvey (based on simpleSAMLphp)

The limesurvey-saml-0.2 works with limesurvey 2.06+ Build 160129


This plugin allow you enable different workflows:

1. SAML ONLY

    Allow to only let saml authentication login.

    When the user access to the login page, he will be redirected to the IdP. After authenticate:
 
      a) If is the first time, the user account will be created (stored in the file)

      b) If the account already exists, the user account will be updated (stored in the file)


    HOW get that mode?

    Easy, check the param 'force_saml_login' of the plugin configuration


2. INTERNAL AUTH BACKEND + SAML

    Enable SAML as an extra authentication backend. (Keep 'force_saml_login' disabled)



Author
------

Alexander Brychcy <alexander@brychcy.net>

based on initial release by Sixto Martin Garcia: https://github.com/pitbulk/limesurvey-saml

License
-------

GPL2 http://www.gnu.org/licenses/gpl.html


How install and enable the SAML plugin
--------------------------------------

This plugin requires a [simpleSAMLphp instance configured as an SP](http://simplesamlphp.org/docs/stable/simplesamlphp-sp)

If your SP is ready, you will be able to enable your SAML plugin in order to add SAML support to your Limesurvey instance.


Copy the AuthSAML folder inside the folder plugins

Access to the Limesurvey platform, enable the SAML plugin and configure the following parameters:

 * simplesamlphp_path: Path to the SimpleSAMLphp folder  (Ex. /var/www/simplesamlphp )

 * saml_authsource: SAML authentication source. (Review what value you set in your simpleSAMLphp SP instance (config/authsource.php)

 * saml_uid_mapping: SAML attribute used as username

 * saml_mail_mapping: SAML attribute used as email

 * saml_name_mapping: SAML attribute used as name

 * saml_groups_mapping: SAML attribute used as groups
 
 * authtype_base: Authtype base. Use 'Authdb' if you do not know what value use.

 * storage_base: Storage base, Use 'DbStorage' if you do not know what value use.

 * auto_create_users: Let the SAML auth plugin create new users on limesurvey.

 * auto_update_users: Let the SAML auth plugin update users on limesurvey.

 * auto_create_groups: Let the SAML auth plugin create new groups on limesurvey.

 * auto_update_groups: Let the SAML auth plugin update groups on limesurvey.
 
 * force_saml_login: Enable it when you want to only allow SAML authentication on limesurvey (no login form will be showed)

