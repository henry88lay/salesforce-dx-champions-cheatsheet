# Salesforce DX Cheatsheet
SFDX commands are categorised by namespaces, with the most significant being the following:
```
force
config
alias
auth
```
## Force Namespace
The force namespace consists of the most commonly and widely used SFDX commands.
They consist of numerous tools for developement on the Salesforce Platform.

### Org Commands
Use these commands to manage your orgs within Salesforce CLI.
Useful for creating, deleting, authorizing and opening your org environments.

### force:org:create

Why do we use it?
- To create a scratch org or sandbox.

How do we use it?

- `sfdx force:org:create -f config/enterprise-scratch-def.json -a MyScratchOrg -v devHub` - When creating a new scratch org, the targetdevhubusername (`-v`) must be a Dev Hub org whilst the configuration file is specified with `-f`.

When do we use it?
- When a new environment for developing a workplace item is required.

Documentation:
[force:org:create](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_create)

### force:org:delete

Why do we use it?
- To delete a scratch org or sandbox.

How do we use it?
- `sfdx force:org:delete -u MyOrgAlias` - Utilise the `-u` parameter to name the environment for deletion.

When do we use it?
- When an environment is deemed to be no longer required for use.

Documentation:
[force:org:delete](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_delete)

### force:org:display

Why do we use it?
- To display key information about the target org.

How do we use it?
- `sfdx force:org:display -u TestOrg1` - Utilise the `-u` parameter to select the org to display.

When do we use it?
- When information about the target org is required. Particularly useful in
showing login credentials.

Documentation:
[force:org:display](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_display)

### force:org:list

Why do we use it?
- To display a list of currently authorized orgs.

How do we use it?
- `sfdx force:org:list`

When do we use it?
- When working in multiple environments, this command is helpful in identifying the different orgs
 you are currently working in. It provides useful information regarding alias name,
 user name, the current default org (designated with a subsequent (U)) and org expiry dates.

Documentation:
[force:org:list](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_list)

### force:org:open

Why do we use it?
- To open the current or targetted org.

How do we use it?
- `sfdx force:org:open -u MyTestOrg`

When do we use it?
- When we would like to quickly open a authenticated org.

Documentation:
[force:org:open](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_org.htm#cli_reference_force_org_open)


### Source Commands
Use these commands to push and pull source from your environments.
Useful for pulling applied changes from an org to then commit to a repository or
pushing componenets of a repository to a specific environment.

### force:source:pull

Why do we use it?
- To pull all source from a scratch org to a repository.

How do we use it?
- `sfdx force:source:pull -u targetOrg`

When do we use it?
- Most commonly used on scratch orgs that have minimal changes or are simplistic in build.
Although useful, this command can be difficult to use as repository to org discrepencies will
cause the command to fail without completing the process.
An alternative to this is using force:org:retrieve (see below).

Documentation:
[force:source:pull](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_source.htm#cli_reference_force_source_pull)

### force:source:push

Why do we use it?
- To push all source from a repository to a scratch org.

How do we use it?
- `sfdx force:source:push -u targetOrg`

When do we use it?
- Most commonly used to push to scratch orgs that have a simplistic build.
Although useful, this command can be difficult to use as repository to org discrepencies will
cause the command to fail without completing the process.
An alternative to this is using force:org:deploy (see below).

Documentation:
[force:source:push](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_source.htm#cli_reference_force_source_push)

### force:source:retrieve

Why do we use it?
- To retrieve certain metadata from an org to repository.

How do we use it? <br />
To retrieve source files in a directory:
- `sfdx force:source:retrieve -p path/to/source -u targetOrg` <br />

To retrieve all Apex Classes in the org:
- `sfdx force:source:retrieve -m ApexClass` - The `-m` tag can be used to target any metadata within the org.

When do we use it?
- To retrieve particular metadata from an org. Note that the source retrieved overwrites
the corresponding source files in your local filesystem.

Documentation:
[force:source:retrieve](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_source.htm#cli_reference_force_source_retrieve)

### force:source:deploy

Why do we use it?
- To deploy certain metadata to an org from a repository.

How do we use it? <br />
To deploy source files in a directory:
- `sfdx force:source:deploy -p path/to/source -u targetOrg` <br />

To deploy all Apex Classes to the org:
- `sfdx force:source:deploy -m ApexClass` - The `-m` tag can be used to deploy any metadata to the org.

When do we use it?
- To deploy particular metadata to an org. Note that the source deployed overwrites
the corresponding source files in your org.

Documentation:
[force:source:deploy](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference_force_source.htm#cli_reference_force_source_deploy)
