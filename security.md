## JWT security validation on microservice project
  - Setup the .npmrc with your authToken for gitlab registry
    ```
      ...
      //gitlab.com/api/v4/packages/npm/:_authToken=<gitlab_generated_auth_token>
      @pagofx:registry=https://gitlab.com/api/v4/packages/npm/
      ...
    ```
  - Import security library on package.json, with the last version published ```npm install @pagoxf/security```
    ```
      ...
      "@pagofx/security": "1.0.0-pfxb-361.0.2.0",
      ...
    ```
  - Call the middleware before the router on the main app file, src/app/index.ts by default
    ```
      ...
      import { authorizationMiddleware } from '@pagofx/security';
      ...
      app.use(authorizationMiddleware());
      ...
    ```