# Automate the review process
GitHub Actions can run multiple workflows for different event triggers. Let's create a new approval workflow that'll work together with our Node.js workflow.
# step 1
set the nodejs templated workflow file 
# step 2 
create a file for the approval automation
``` approval-workflow.yml```
 Enter a name for your workflow in the new file
``` name: team moneymoh approval workflow```
# step 3
create an event
```on: pull_request_review```
# step 4
add job
```labelWhenApproved:```
 we'll use an action that adds a label to any pull requests after a preset number of approvals


# Add a step
We've now got a job with the labelWhenApproved
to use a community action, use the uses: keyword
label-when-approved-action requires a block called env:
with the following environment variable
* APPROVALS is the number of required approvals that are required for a label to be applied, please set this to "1"
* GITHUB_TOKEN is necessary so the action can create and apply labels to this repository. 

* ADD_LABEL is the name of the label which should be added when the number of approvals have been met, choose any label name you wish
# add branch protection rules to  avoid merging to the wrong branch


