---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Known issues with {{site.data.keyword.name-da}} deployable architectures
{: #known-issues}

Because issues change frequently, check this list regularly.
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

To finish undeploying, wait for about 15 minutes and then retry.
