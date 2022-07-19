# Salesforce DX Cheatsheet

## Useful Commands
SFDX commands are categorised by namespaces, with the most significant being the following:
- force
- config
- alias
- auth

### Force Namespace
The force namespace consists of the most commonly and widely used SFDX commands.
They consist of numerous tools for developement on the Salesforce Platform.

#### Org Commands
Use these commands to manage your orgs within Salesforce CLI.
Useful for creating, deleting, authorizing and opening your org environments.

##### Force:org:create

Why do we use it?
To create a scratch org or sandbox.

How do we use it?
'sfdx force:org:create -f config/enterprise-scratch-def.json -a MyScratchOrg'

When creating a new scratch org, the targetdevhubusername ('-v') must be a Dev Hub org
whilst the configuration file is specified with '-f'.

When do we use it?
When a new environment for developing a workplace item is required.

Documentation:
https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_create

##### Force:org:delete

Why do we use it?
To delete a scratch org or sandbox.

How do we use it?
'sfdx force:org:delete -u MyOrgAlias'

Utilise the '-u' parameter to name the environment for deletion.

When do we use it?
When an environment is deemed to be no longer required for use.

Documentation:
https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_delete

##### Force:org:display

Why do we use it?
To display key information about the target org.

How do we use it?
'sfdx force:org:display -u TestOrg1'

Utilise the '-u' parameter to select the org to display.

When do we use it?
When information about the target org is required. Particularly useful in
showing login credentials.

Documentation:
https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_display

##### Force:org:list

Why do we use it?
To display a list of currently authorized orgs.

How do we use it?
'sfdx force:org:list'

When do we use it?
When working in multiple environments, this command is helpful in identifying the different orgs
 you are currently working in. It provides useful information regarding alias name,
 user name, the current default org (designated with a subsequent (U)) and org expiry dates.

Documentation:
https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_list

##### Force:org:open

Why do we use it?
To open the current or targetted org.

How do we use it?
'sfdx force:org:open -u MyTestOrg'

When do we use it?
When we would like to quickly open a authenticated org.

Documentation:
https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_open