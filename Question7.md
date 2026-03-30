Describe the governance measures you would apply when deploying AI systems in an enterprise environment? 

1. Architecture GOvernance:
i. Ensure separate environents are available and used correctly for development, staging and production
ii. Ensure there are separate pipelines for storage, ingestion, processing and so on to reduce failure and risk points.
iii. Ensure each of the environments have well established access controls, especially and read and write permissions.
iv. Ensure there are flexible rollout and rollback mechanisms and methods like canary deployments to ensure lesser down times in times of failed rollouts.

2. Data & Model Governance:
i. Include regular human/user feedback loops to ensure model is performing as required.
ii. Perform frequent checks to look for hallucinations and data drifts. This can be done by introducing human-in-the-loop to validate the outputs regularly.
iii. Ensure there are easy to follow and clear instructions for error management where an issue can be easily raised and corrected if there are issues with the model.

3. Security Governance:
i. Ensure private endpoints are used for critical systems such as Azure AI Search.
ii. Enfore stronger input sanitization to prevent prompt injections that can break into the system.
iii. ensure proper role based access controls and attribute based access controls are in place on different resources.