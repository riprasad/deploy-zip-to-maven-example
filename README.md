# Apicurio Registry Installation and Example Files

## Configuration

This project uses [Kustomize](https://kustomize.io/) to configure the following installation details:

* Installation namespace
* Operator image name
* Registry image names

Update those details according to each product release.

## How to Install the Operator

Create a project with the name defined in the `namespace` field in `install/kustomization.yaml`. The default is `apicurio-registry`.

```
oc new-project <NAMESPACE>
```

Apply the Resources located in the `install/` folder:

```
oc apply -k ./install/
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
