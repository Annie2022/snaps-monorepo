# snaps-skunkworks

Private monorepo for experimental snaps dependencies.

## Contributing

### Installing

Run `yarn setup` in the project root directory.
Do **not** run any installation commands in individual workspaces.

If you add a dependency with a lifecycle script, said dependency must be added to the `devDependencies` and `lavamoat.allow-scripts` config of the root `package.json` file.
This is currently the only way to use `@lavamoat/allow-scripts` in monorepos.

### Building

For local development, you should run `yarn build:clean` in the project root directory.
This will always build the packages in the correct order.

You can also run `yarn build` in a workspace, although you have to ensure that the projects are built in the correct order.

Repository-wide watching is currently not possible due to the build processes of some packages.

### Testing and Linting

Run `yarn test` and `yarn lint` in the project root directory, or in a workspace.

### Publishing

Follow the usual release automation workflow, the publish locally from the monorepo root using:

```sh
yarn publish:all --otp=YOUR_NPM_OTP_CODE
```
