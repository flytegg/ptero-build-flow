# ptero-build-flow
Automatically build and deploy a Gradle project to a Pterodactyl server instance, and restart it.

## How to use

### Output jar

Ensure that your output jar is named the same as the repository. For example is your GitHub repository is called "example" then your output jar should be called `output.jar`.

To do this with shadowJar, you can add this to your shadowJar task:
```kt
shadowJar {
    archiveFileName.set("example.jar")

    // the rest of your configuration
}
```

### Set up repository Actions Secrets & Variables

#### Variables

- `PTERO_HOST` - This needs to be the host url of your Pterodactyl panel, e.g. `panel.flyte.gg`
- `PTERO_SERVER_ID` - This needs to be the server id you wish to deploy to, e.g. `c6f88cfb` (the first sector of the UUID)

#### Secrets

- `PTERO_API_KEY` - This is a Client/Account API key, generated at /account/api (not to be mistaken with an Application API key - /admin/api)

### Java Version

If you need, you can change the JDK vendor and version in the "Set up JDK 17" step.
