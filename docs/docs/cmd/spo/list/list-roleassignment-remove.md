# spo list roleassignment remove

Removes a role assignment from list permissions

## Usage

```sh
m365 spo list roleassignment remove [options]
```

## Options

`-u, --webUrl <webUrl>`
: URL of the site where the list is located

`-i, --listId [listId]`
: ID of the list. Specify either listId, listTitle or listUrl but not multiple.

`-t, --listTitle [listTitle]`
: Title of the list. Specify either listId, listTitle or listUrl but not multiple.

`--listUrl [listUrl]`
: Relative URL of the list. Specify either listId, listTitle or listUrl but not multiple.

`--principalId [principalId]`
: SharePoint ID of principal it may be either user id or group id we want to remove permissions Specify principalId only when upn or groupName are not used.

`--upn [upn]`
: upn/email of user. Specify either upn or princpialId.

`--groupName [groupName]`
: enter group name of Azure AD or SharePoint group. Specify either groupName or princpialId.

--8<-- "docs/cmd/_global.md"

## Examples

Remove roleassignment from list by title based on group name

```sh
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listTitle "someList" --groupName "saleGroup"
```

Remove roleassignment from list by title based on principal Id

```sh
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listTitle "Events" --principalId 2
```

Remove roleassignment from list by url based on principal Id

```sh
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listUrl '/sites/contoso-sales/lists/Events' --principalId 2
```