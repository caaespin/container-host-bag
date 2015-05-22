## About container-host-bag

This project consists of a set of Ansible playbooks that allow you to deploy a host running Docker with a set of dependencies for running pan-cancer workflows. 

See recommended parameters at [example\_params.json](example_params.json)


## For DKFZ/EMBL
If you are going to run the DKFZ/EMBL workflow, you will need to run the DEWrapperWorkflow playbook. To do this, ensure that you specify `DEWrapper` in your json variables:

    "workflow_name":"DEWrapper",
    "workflows":["Workflow_Bundle_DEWrapperWorkflow_1.0.2_SeqWare_1.1.0","Workflow_Bundle_HelloWorld_1.0-SNAPSHOT_SeqWare_1.1.0"]    

Alternatively, if using Bindle config files to specify variables, use the following

    install_workflow = True
    workflow_name = DEWrapper
    workflows=Workflow_Bundle_DEWrapperWorkflow_1.0.2_SeqWare_1.1.0,Workflow_Bundle_HelloWorld_1.0-SNAPSHOT_SeqWare_1.1.0

## TODO

Note that for the DKFZ/EMBL workflow, a large batch of dependency files needs to be in the /datastore directory. However, this directory may be ephemeral (for example when using lvm). This means that the Amazon image process will not retain this information. In practice, this probably just means re-running this playbook via youxia deployment and most steps will be skipped. 
