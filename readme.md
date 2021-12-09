[comment]: # "Auto-generated SOAR connector documentation"
# NSX

Publisher: VMware  
Connector Version: 1\.0\.3  
Product Vendor: VMware  
Product Name: NSX  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 3\.0\.251  

This app implements investigative and management action on VMware NSX, Network Virtualization and Security Platform

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a NSX asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**nsx\_manager** |  required  | string | NSX Manager IP/Hostname
**verify\_server\_cert** |  required  | boolean | Verify server certificate
**username** |  required  | string | Administrator username
**password** |  required  | password | Administrator password

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[block port](#action-block-port) - Block an application port  
[block ip](#action-block-ip) - Block an IP  
[create tag](#action-create-tag) - Create Security Tag  
[create group](#action-create-group) - Create Security Group  
[add tag](#action-add-tag) - Attach Security Tag  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'block port'
Block an application port

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**port** |  required  | L4 Port to block | numeric |  `port` 
**protocol** |  required  | IP Protocol number to block | numeric |  `protocol` 
**ip** |  required  | IP to block \(optional\) | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.port | numeric |  `port` 
action\_result\.parameter\.protocol | numeric |  `protocol` 
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'block ip'
Block an IP

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to block | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'create tag'
Create Security Tag

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**tag** |  required  | Security Tag to create | string |  `nsx tag` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.tag | string |  `nsx tag` 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'create group'
Create Security Group

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**group** |  required  | Security Group to create | string |  `nsx group` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.group | string |  `nsx group` 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'add tag'
Attach Security Tag

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**tag** |  required  | Name of Security Tag to attach | string |  `nsx tag` 
**vmobjectid** |  required  | vCenter VM ObjectID,Eg\: vm\-104 | string |  `nsx vmobjectid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.tag | string |  `nsx tag` 
action\_result\.parameter\.vmobjectid | string |  `nsx vmobjectid` 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 