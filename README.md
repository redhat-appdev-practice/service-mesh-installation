## Consultant 360 OCP Infrastructure
This playbook will create all the resources required for the consultant 360 application.

[https://console-openshift-console.apps.shared-dev.dev.openshift.opentlc.com/](OCP 4.1 Cluster)

#### Openshift Applier
```
ansible-galaxy install -r requirements.yml -p roles
```

#### Executing the playbook

##### Bootstrapping Projects and Creating Roles
```
ansible-playbook site.yml -i inventory/hosts -l bootstrap
```

##### Deploying Consultant 360 Applications
```
ansible-playbook site.yml -i inventory/hosts -l consultant360
```

<div class="panel panel-warning">
**Mac Users**
{: .panel-heading}
<div class="panel-body">

A recent update as placed a limit of the number of forks a process can create. To disable this, set **OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES**

</div>
</div>