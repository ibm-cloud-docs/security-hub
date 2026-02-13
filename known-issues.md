---

copyright:
  years: 2024
lastupdated: "2026-02-13"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Known issues with Cloud foundation for security and observability deployable architecture
{: #known-issues}

Learn about the following known issues and limitations for the Cloud foundation for security and observability deployable architecture. Issues can change frequently, so be sure to check back regularly or view the release notes to see when they're resolved.
{: shortdesc}

## Error when you try to undeploy key management
{: #ki-kms-undeploy}

When you try to undeploy the key management member of the deployable architecture, you might see an error that's similar to the following error:

```hcl
"Result": {
  "details": "{\"status_code\":409,\"name\":\"ConflictError\",\"message\":{\"message\":\"CONTAINS_ACTIVE_KEYS: Remove all keys before de-provisioning: Instance contains 4 active keys\",\"name\":\"ConflictError\",\"status_code\":409,\"transaction_id\":\"\"},\"description\":\"CONTAINS_ACTIVE_KEYS: Remove all keys before de-provisioning: Instance contains 4 active keys\"}",
  "error_code": "RC-ServiceBrokerErrorResponse",
  "message": "Please contact the Service Provider for this error. [409, Conflict] CONTAINS_ACTIVE_KEYS: Remove all keys before de-provisioning: Instance contains 4 active keys",
  "status_code": 422,
  "transaction_id": "bss-bc223e693444d810"
}
```
{: screen}

To finish undeploying, wait 15 minutes and then retry.
