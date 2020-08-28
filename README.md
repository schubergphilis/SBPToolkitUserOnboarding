# SBP Toolkit Services Onboarding

This repository comes pre-staged with two files which are required to deploy services in a service group:

- azure-pipelines.yml - the pipeline definition
- services.json - the definition of the services topology

Before running the pipeline be sure to adjust the contents of both files.

## YAML Pipeline Definition

The pipeline definition comes provided with five stages - the build stage with will publish local artifacts to use in deployments, and four stages which represent environments. The predefined environments represent the default four stages of a DTAP street, with only the DEV being enabled out of the box. To enable other stages remove the comment characters at the beginning of each line. Also, adjust the names and order to meet your specific requirements.

Before running the pipeline for the first time, be sure to adjust the two variables:

location: 'Replace West Europe with the desired location'
servicveGroup: 'Replace the placeholder value - svgr with the desired four-letter short-code'

Please also be mindful that the pipeline relies on a YAML template for the build stage which is, by default, stores in a separate, central repository - sources. If you're not implementing that repo, please adjust the contents accordingly.

## JSON Services Topology Definition

The service topology definition comes provided with two services:

- core - to hold basic resources which are expected to be needed in most cases (Key Vault, Log Analytics, etc.)
- network - to hold the virtual network components

Please adjust the topology to fit your needs. You may choose to only add items to the array or completely change it by removing to ones provided out of the box. Should you choose to remove the pre-staged services, please be mindful that the starter infra pipeline will target them by default, so it would also have to be adjusted.

Before running the pipeline for the first time, be sure to adjust the property:

"serviceGroup": "Replace the placeholder value - svgr with the desired four-letter short-code"
