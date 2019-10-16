## To publish to npm

1. Run `npm run build` to create the dist folder (ensure tsconfig.json is set to copy the build there)
1. Run `npm publish --access public` and enter the 2FA code for npm in 1Password

## Running directly gives RxJs error

Have to run `npm install` at the root of the project as well as in the samples originally. Changed the sample to reference
the package directly now though.

## To run samples with local Observable Store Code for testing

1. Run `npm install` at root of the project
1. Remove `@codewithdan/observable-store` from `package.json` file for sample.
1. Change the import in the service(s) from:

    `import { ObservableStore } from '@codewithdan/observable-store';`

    To:

    `import { ObservableStore } from '../../../../../src/observable-store';`

1. Delete `node_modules` and run `npm install` again for the sample project.
1. Run `ng server -o`

## To run the Observable Store npm module locally without publishing to npm

1. Run `npm link` at the root of the project
1. Go into the target sample project and run `npm link @codewithdan/observable-store`

When done you can unlink by running `npm unlink @codewithdan/observable-store` in the target sample project