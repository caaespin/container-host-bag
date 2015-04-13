## About container-host-bag

This project consists of a set of Ansible playbooks that allow you to deploy a host running Docker with a set of dependencies for running pan-cancer workflows. 


## For DKFZ/EMBL
If you are going to run the DKFZ/EMBL workflow, you will need to run the DEWrapperWorkflow playbook. To do this, ensure that you specify `DEWrapper` in your config file:


    install_workflow = True
    workflow_name = DEWrapper
    workflows=Workflow_Bundle_DEWrapperWorkflow_1.0-SNAPSHOT_SeqWare_1.1.0-rc.1

On your launcher, you must also have valid AWS configuration files as:

    ~/.aws/config
    ~/.aws/credentials

These files are need by part of the DEWrapper playbook. If you don't have a valid AWS login, the playbook will fail.
