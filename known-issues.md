---

copyright:
  years: 2024
lastupdated: "2025-05-02"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Known issues with Essential Security and Observability Services deployable architecture
{: #known-issues}

Learn about the following known issues and limitations for the Essential Security and Observability Services deployable architecture. Issues can change frequently, so be sure to check back regularly or view the release notes to see when they're resolved.
{: shortdesc}

## Name clash when integrating {{site.data.keyword.compliance_short}} with {{site.data.keyword.en_short}}
{: #scc-en-name-clash}

By default the {{site.data.keyword.compliance_short}} deployable architecutre will use a source name called "compliance" when it configures integration with an {{site.data.keyword.en_short}} instance. This source name has to be unique in the {{site.data.keyword.en_short}} instance, so if you have several {{site.data.keyword.compliance_short}} instances configured to use the same Event Notifications instance, it is possible the integration configuration will fail with the error `Source name already exists in Event Notifications instance`.

### Workaround
{: #scc-en-name-clash-workaround}

It is possible to set the source name used to prevent this error by changing the value of the `en_source_name` input variable in the {{site.data.keyword.compliance_short}} deployable architecutre.

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
