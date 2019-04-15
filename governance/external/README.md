This repository contains an example of using a data source that calls a function together with a Sentinel policy that checks the result returned by the function call. While the example here just trivially runs a shell script that returns different values based on the account number passed to it by the Terraform code, a customer could actually call an external API to capture real data and then have Sentinel check the result.

There is a commented out line, `#(length(check_account_balance) > 0) and`, which if uncommented would require the check_balance data source to be present in every single workspace in the current organization. Enable this with caution since any workspace that did not have this data source would cause hard-mandatory failure of this policy.