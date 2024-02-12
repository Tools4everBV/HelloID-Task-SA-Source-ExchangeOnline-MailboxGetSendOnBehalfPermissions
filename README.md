# HelloID-Task-SA-Source-ExchangeOnline-MailboxGetSendOnBehalfPermissions

## Prerequisites
- [ ] This script uses the Exchange Online Management PowerShell Module and requires an App Registration with App permissions:
  - [ ] Manage Exchange As Application <b><i>Exchange.ManageAsApp</i></b>
- [ ] And a role with the permissions for Exchange Online:
  - [ ] The **Exchange Administrator** role should provide the required permissions for any task in Exchange Online PowerShell. However, some actions may not be allowed, such as managing other admin accounts, for this the Global Administrator would be required. Please note that the required role may vary based on your configuration.

## Description

This code snippet executes the following tasks:

1. Imports the ExchangeOnlineManagement module.
2. Define `$mailboxGuid` based on the `selectedMailbox` data source input `$datasource.selectedMailbox.Guid`
3. Creates a session to Exchange Online.
4. List all recipients in Exchange Online with `SendOnBehalf` permissions to the mailbox using the cmdlet: [Get-Mailbox](https://learn.microsoft.com/en-us/powershell/module/exchange/get-mailbox?view=exchange-ps)
5. Return a hash table for each user account using the `Write-Output` cmdlet.

> To view an example of the data source output, please refer to the JSON code pasted below.

```json
{
  "selectedMailbox": {
    "Guid": "7d53a91f-dd9d-41b3-94fb-143bd2fc6854"
  }
}
```