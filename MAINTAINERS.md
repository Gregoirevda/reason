## Releasing Native Packages To Npm:

There's a few native `esy` packages included which are released to npm.

- `reason`
- `rtop`
- `rebuild`
These are combined together into a separate package `reason-cli` which
prebuilds those as well as merlin. They can also be used individually from
`esy` projects without prebuilding, but they are more or less just npm hosted
versions of the Opam packages.


    git checkout -b MYRELEASE origin/master
    git rebase origin/master
    vim -O esy.json scripts/esy/esy.reason.json
    # Then edit the version number accordingly on BOTH files.
    git commit - "Bump version"
    git push origin HEAD:PullRequestForVersion
    node ./scripts/esy-prepublish.js

Then follow the printed instructions for pushing any of the packages to npm.
They will show up under `@esy-ocaml/reason` etc.

## Releasing rtop/rebuild

`rtop` and `rebuild` are also separate `esy` packages hosted on `npm`. You can
release them in the same way as you released the `reason` package


## When a new version of Reason is pushed, you might like to release some
prebuilt global installs of refmt, and merlin together in one npm instal.
`reason-cli` is the project that performs that task, and it packages up
prebuilts of the packages you already pushed to npm above.

See the [https://github.com/reasonml/reason-cli](reason-cli) page for
instructions on performing that release.

## Releasing Native Packages To Opam:

TODO
