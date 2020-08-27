# The purpose of this repo is only to explain a bug inside @nrwl/nx angular's build

As you can see I've created two project, one with nx9 and the other with nx10.
if you run `yarn start:9` inside the nx9test folder the application will start correctly.
Instead if you run `yarn start:10` an error during the build process will be showed.

This error is related tho the impossibility of scss-loader to find the correct path of the font asset. In particular `Can't resolve './css/assets/font/fontello.eot'`. As you can see the path is incorrect and this is maybe related to this file [https://github.com/nrwl/nx/blob/10.0.x/packages/web/src/utils/third-party/cli-files/models/webpack-configs/styles.ts](https://github.com/nrwl/nx/blob/10.0.x/packages/web/src/utils/third-party/cli-files/models/webpack-configs/styles.ts), this commit [https://github.com/nrwl/nx/commit/5b6df63](https://github.com/nrwl/nx/commit/5b6df63).