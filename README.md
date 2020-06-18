# Apicurio Registry Installation and Example Files

## How to Install the Operator

Create a project for the installation, e.g., `apicurio-registry`.

```
oc new-project <NAMESPACE>
```

Set the namespace in `install/cluster_role_binding.yaml`.

Apply the files located in the `install/` folder:

```
oc apply -f install/
```

## How to Install the Registry

The registry supports the following persistence solutions:

* In-memory
* Infinispan
* PostgreSQL
* Kafka
* AMQ Streams

Examples of ApicurioRegistry Custom Resources configured for different persistence solutions can be found in the `examples/` folder. Apply one of them:

```
oc apply -f ./examples/apicurioregistry_<PERSISTENCE>_cr.yaml -n <NAMESPACE>
```
