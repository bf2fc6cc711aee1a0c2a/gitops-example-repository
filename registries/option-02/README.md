# Option 2

This is an option with simplified structure. Features:
 - Minimal number of resource files:
   - service (control plane, global Registry configuration)
   - group
   - artifact (includes list of versions and content metadata)
   
   but e.g. content may be separated.
 - Using schema references inspired by AppSRE for validation and versioning (useful for non-k8s-type resources)
 - The content can be organized into any structure, i.e. no requirements on content file names
