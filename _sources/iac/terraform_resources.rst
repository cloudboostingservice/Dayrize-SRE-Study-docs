Terraform Resources
===================

The following is a list of the Terraform resources managed by this configuration, along with their types and links to the official Terraform registry for more details.

.. list-table::
   :header-rows: 1
   :widths: 30 70

   * - Name
     - Type
   * - `google_app_engine_standard_app_version.dayrize_app_v1 <https://registry.terraform.io/providers/hashicorp/google/5.18.0/docs/resources/app_engine_standard_app_version>`_
     - resource
   * - `google_firestore_database.database <https://registry.terraform.io/providers/hashicorp/google/5.18.0/docs/resources/firestore_database>`_
     - resource
   * - `google_project_iam_member.service_account_roles <https://registry.terraform.io/providers/hashicorp/google/5.18.0/docs/resources/project_iam_member>`_
     - resource
   * - `google_project_service.api <https://registry.terraform.io/providers/hashicorp/google/5.18.0/docs/resources/project_service>`_
     - resource
   * - `google_service_account.custom_service_account <https://registry.terraform.io/providers/hashicorp/google/5.18.0/docs/resources/service_account>`_
     - resource
   * - `google_storage_bucket.bucket <https://registry.terraform.io/providers/hashicorp/google/5.18.0/docs/resources/storage_bucket>`_
     - resource
   * - `google_storage_bucket_object.object <https://registry.terraform.io/providers/hashicorp/google/5.18.0/docs/resources/storage_bucket_object>`_
     - resource

Terraform Inputs
================

This section details the input variables required to configure the Terraform resources. The table includes a description, type, default values, and if they are required.

.. list-table::
   :header-rows: 1
   :widths: 20 40 10 10 10

   * - Name
     - Description
     - Type
     - Default
     - Required
   * - AUTH0_CLIENT_ID
     - Environment variable
     - `string`
     - n/a
     - yes
   * - AUTH0_DOMAIN
     - Environment variable
     - `string`
     - n/a
     - yes
   * - LOG_LEVEL
     - Environment variable
     - `string`
     - n/a
     - yes
   * - account_identifier
     - Account Identifier
     - `string`
     - n/a
     - yes
   * - apis
     - n/a
     - `list(string)`
     - n/a
     - yes
   * - database_name_fs
     - database firestore name
     - `string`
     - n/a
     - yes
   * - entrypoint
     - command to run app
     - `string`
     - n/a
     - yes
   * - location
     - location all resources
     - `string`
     - n/a
     - yes
   * - name_bucket
     - name bucket
     - `string`
     - n/a
     - yes
   * - name_file_app
     - name app
     - `string`
     - n/a
     - yes
   * - port
     - service port
     - `string`
     - n/a
     - yes
   * - project_id
     - project name
     - `string`
     - n/a
     - yes
   * - roles
     - Map of roles for the service account
     - `map(string)`
     - n/a
     - yes
   * - runtime
     - run time
     - `string`
     - n/a
     - yes
   * - service_app_engine
     - name of service
     - `string`
     - n/a
     - yes
   * - source_file_app
     - source file app
     - `string`
     - n/a
     - yes
   * - type_db
     - type database native or datastore
     - `string`
     - n/a
     - yes
   * - url_base
     - url base file app
     - `string`
     - n/a
     - yes
   * - version_app
     - version App
     - `string`
     - n/a
     - yes

Outputs
=======

This configuration currently does not define any outputs.
