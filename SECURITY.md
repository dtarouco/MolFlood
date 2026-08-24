# Security Policy

## Serialized model warning

MolFlood currently uses Joblib serialization for trained model artifacts.

Python serialized artifacts from untrusted sources may execute code when loaded. Never load an unreviewed `.joblib` artifact in a trusted environment.

Community-submitted models must not be automatically deserialized merely because they were submitted.

## Data safety

Do not upload confidential, proprietary, embargoed, patient-derived, or otherwise restricted molecular datasets to public issues or pull requests unless redistribution is explicitly authorized.
