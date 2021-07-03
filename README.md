# Flutter GH Pages

Automates the build and deployment of your Flutter web app on Github gh pages

# Action

To use this action, create an action like the following on your workflows folder

```yml
name: Gh-Pages

on:
  push:
    branches: [ master ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2 # Only works with v2
      - uses: subosito/flutter-action@v1
      - uses: erickzanardo/flutter-gh-pages@v4
```
To build a project in a folder other that the root, use the `workingDir` property

```yml
      ...
      - uses: erickzanardo/flutter-gh-pages@v4
        with:
          workingDir: example
```

By default, the action will use the auto setting for web renderers, to change that you can use the `webRenderer` property.

More on web renderers here: https://flutter.dev/docs/development/tools/web-renderers

```yml
      ...
      - uses: erickzanardo/flutter-gh-pages@v4
        with:
          webRenderer: canvaskit
```

To pass arguments to the builder with `--dart-define` the `dartDefine` property can be used

```yml
      ...
      - uses: erickzanardo/flutter-gh-pages@v4
        with:
          dartDefine: "customArg=TEST"
```

To use github pages with a custom domain, add a file named `CNAME` to the
`<project>/web` folder whose contents is your domain, like:
> subdomain.domain.com
