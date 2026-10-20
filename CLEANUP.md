# Cleanup and cost guidance

## Core exercises: no cloud resources required

The core workshop runs in a chat playground with a document attached or pasted. It does **not** require provisioning Azure AI Foundry projects, storage accounts, vector databases, app services, or APIs.

## After the lab

1. Delete temporary chats, uploaded training documents, and test files from the playground if they are no longer needed; follow the provider's retention settings.
2. Remove any temporary API keys or environment variables created for optional experimentation; rotate any key accidentally shared.
3. If you created an optional **cloud deployment**, locate and delete its project, resource group, associated storage/search resources, endpoints/deployments, and any other resources **created solely for the workshop**. Verify dependencies and ownership before deletion; do not delete shared classroom or production resources.
4. Check the cloud billing/cost dashboard after cleanup; some costs can lag.
5. Confirm there are no active paid endpoints, scheduled jobs, or usage-based services left running.

## Cost precautions

- Prefer an instructor-provided playground or a free quota with limits.
- Review current provider pricing; inference and file storage may incur charges even without a dedicated deployment.
- If using Azure or another cloud, set a budget/alerts before creating resources. **Alerts do not necessarily cap spending.**
- Do not publish subscription IDs, access tokens, API keys, or billing details in GitHub.
