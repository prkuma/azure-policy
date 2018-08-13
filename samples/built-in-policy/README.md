## Audit enablement of encryption of Automation account variables

It is important to enable encryption of Automation account variable assets when storing sensitive data.

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/?feature.customportal=false&microsoft_azure_policy=true&microsoft_azure_policy_policyinsights=true&feature.microsoft_azure_security_policy=true&microsoft_azure_marketplace_policy=true#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-policy%2Fmaster%2Fsamples%2Fbuilt-in-policy%2Faudit-automation-account-variable-encryption2Fazurepolicy.json)

## Try with Powershell

````powershell
$definition = New-AzureRmPolicyDefinition -Name "audit-automation-account-variable-encryption" -DisplayName "Audit enablement of encryption of Automation account variables" -description "It is important to enable encryption of Automation account variable assets when storing sensitive data." -Policy 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/built-in-policy/audit-automation-account-variable-encryption/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/built-in-policy/audit-automation-account-variable-encryption/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzureRMPolicyAssignment -Name <assignmentname> -Scope <scope> -PolicyDefinition $definition
$assignment 
````

## Try with CLI

````cli
az policy definition create --name 'audit-automation-account-variable-encryption' --display-name 'Audit enablement of encryption of Automation account variables' --description 'It is important to enable encryption of Automation account variable assets when storing sensitive data.' --rules 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/built-in-policy/audit-automation-account-variable-encryption/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/built-in-policy/audit-automation-account-variable-encryption/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "audit-automation-account-variable-encryption" 
````