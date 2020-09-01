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
      - uses: actions/checkout@v2
      - uses: subosito/flutter-action@v1
        with:
          channel: 'beta'
      - uses: erickzanardo/flutter-gh-pages@v1
```

To make the build using canvas kit, use the `useCanvasKit` property

```yml
      ...
      - uses: erickzanardo/flutter-gh-pages@v1
        with:
          useCanvasKit: true
```
