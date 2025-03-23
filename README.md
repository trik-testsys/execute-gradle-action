# Execute Gradle Action

This GitHub Action executes Gradle commands in your repository.

## Usage

To use this action, create a workflow file (e.g., `.github/workflows/build.yml`) in your repository with the following content:

```yaml
name: Gradle Build

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Execute Gradle
        uses: trik-testsys/execute-gradle-action@v1
        with:
          distribution: 'adopt-openj9'
          java-version: '17'
          architecture: 'x64'
          gradle-commands: 'build'
```

## Inputs

- `distribution`: The distribution of Java to use (default: `adopt-openj9`)
- `java-version`: The version of Java to use (default: `17`)
- `architecture`: The architecture of the Java version (default: `x64`)
- `gradle-commands`: The Gradle commands to run (default: `build test`)

## Author

Roman Shishkin

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.