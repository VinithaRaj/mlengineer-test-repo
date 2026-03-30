How data access control is enforced? 

1. Authentication - Authenticating the user by making them sign in using their Microsoft Entra ID. This allows the system to know the access groups they are part of.
2. Authorization - By checking against the Access Control List metadata in the indexes of the chunked data, the user's permissions and what the user is privy to can be known.
3. Filtering - Based on the user's role (Role Based Access Control) and attributes (Attribute Based Access Control), several filters can be set, example to limit the documents used in this query to only the documents available to the engineering department.