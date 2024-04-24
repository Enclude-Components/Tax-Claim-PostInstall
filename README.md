# Tax-Claim-PostInstall

### the Tax Claim Package needs to work with both NPSP and NPC
### NPSP uses opportunities for gifts, so fields can be added as part of the standard install
### NPC uses GiftTransactions, so fields can only be added if the object exists - which the package cannot determine
### This unlocked package adds fields to the GiftTransaction object and includes them in a permission set.
### A permission set group allows both the Tax Claim and the Tax Claim NPC permission sets to be assigned to users

## Development

To work on this project in a scratch org:

1. [Set up CumulusCI](https://cumulusci.readthedocs.io/en/latest/tutorial.html)
2. Run `cci flow run dev_org --org dev` to deploy this project.
3. Run `cci org browser dev` to open the org in your browser.

To see changes
    cci task run list_changes --org dev --types CustomField,PermissionSet,PermissionSetGroup --exclude force__
To retrieve changes
    cci task run retrieve_changes --org dev --types CustomField,PermissionSet,PermissionSetGroup --exclude force__
Release unlocked package
    cci flow run release_unlocked_beta --org dev