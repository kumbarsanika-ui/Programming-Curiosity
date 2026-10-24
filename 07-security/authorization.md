# Authorization

Authorization decides whether an authenticated person, service, or process is allowed to perform a particular action on a particular resource.

## Authentication is different

Authentication verifies an identity; authorization checks permissions. A user may be authenticated successfully but still lack permission to view another user's private document or change billing settings.

## Common approaches

Role-based access control gives users roles such as `reader` or `admin`, with permissions assigned to each role. Attribute-based policies decide using facts about the user, resource, action, or context. Systems may combine these approaches.

## Check access at the boundary

The server must enforce permissions for every sensitive operation. Hiding a button in the user interface is not sufficient, because a caller may send a request directly. Follow the principle of least privilege: grant only the permissions needed, and check ownership or scope where appropriate.

Access decisions should fail closed when required information is missing, be tested for both allowed and denied cases, and avoid leaking sensitive details in error messages. See [Authentication](./authentication.md).
