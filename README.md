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

##### Deploying Openshift Operator

```
ansible-playbook site.yml -i inventory/hosts -l istio-operator
```

##### Deploying Openshift Control Plane and Member Roll

```
ansible-playbook site.yml -i inventory/hosts -l istio-system
```

## Mac Users!

> **WARNING:\_** A recent update has placed a limit of the number of forks a process can create. To disable this, set **OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES**

##### Example

```
OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES ansible-playbook site.yml -i inventory/hosts -l consultant360 -e "include_tags=survey-openapi"
```
