This Server Profile is a baseline of PingAccess -- designed to be used with the `PF-Base` (https://github.com/cprice-ping/PF-Base) profile as it's Token Provider.  

## Deployment
* Copy the `docker-compose.yaml` and `env_vars` files to a folder
* Modify the `env_vars` file to match your environment (This should combine the variables needed for *all* components in the Compose stack)
* If the PA Virtual Host is running on anything **other** than `443`, modify the `ports:` section in `docker-compose.yaml` to reflect the mapping to `:3000`
* Launch the stack with `docker-compose up -d`

This PA install provides the following:  
* Proxied connection to https://httpbin.org/anything
* Authenticatied WebSession via PingFed (`client_id` == `PingAccessSession`)
* Forwarded Token is a **Signed** JWT (not the v5.3+ Default of *encrypted*) -- so the contents can be seen on the Target

URL to see PA Protected Application:  
https://${VIRTUAL_HOST_NAME}:${VIRTUAL_HOST_PORT}/anything

**User Credentials:**  
`user.[0-4]` / `2FederateM0re`

**Administrator Console:**
https://${PA_HOSTNAME}:9000  

`Administrator` / `2FederateM0re`