# Option 2

This is an option with simplified structure. Features:
 - Minimal number of resource files:
   - service (control plane, global Registry configuration)
   - group
   - artifact (includes list of versions and content metadata)
   
   but e.g. content may be separated.
 - Using schema references inspired by AppSRE for validation and versioning (useful for non-k8s-type resources)
 - The content can be organized into any structure, i.e. no requirements on content file names

Locking feature:

An idea on how to handle resource naming/uniqueness. For example, RHOSR instance names are unique within an organisation, but name is not an unique identifier both globally and in time. A better identifier would be instance ID. But that is only known after provisioning so if gitops system is creating the instances, it is not known in advance. However, users can add this information afterwards to "lock" the instance, meaning the gitops would be guaranteed to *only* act on that specific instance ID. Similarly for content, we have content hash identifier that does not have to be provided because it can be computed, but including it would ensure content consistency against accidental changes.