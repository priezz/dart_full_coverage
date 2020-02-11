# Helper script for full tests coverage checkup for you Dart/Flutter project

## Installation

1. Clone the script to any location

    ```bash
    wget https://raw.githubusercontent.com/priezz/dart_full_coverage/master/dart-coverage-helper
    ```

2. Make it executable

    ```bash
    chmod +x dart-coverage-helper
    ```

3. Ensure that the location of the script in in your `PATH` environment variable.

    That's it!

## Usage

Run from the root of your Dart/Flutter project

```bash
dart-coverage-helper
```

Then generate the coverage report as usual.

```bash
flutter test --coverage # for Flutter project
# or
pub run test_coverage   # for Dart project
```

(optional) Generate HTML report with [`genhtml`](https://github.com/linux-test-project/lcov) tool

```bash
genhtml -o coverage coverage/lcov.info
```

## How it works

The script just scans your `lib` directory for `*.dart` files (excluding `*.g.dart`) and imports
them into the generated `test/coverage_test.dart` file. This way the coverage analyzers will go
through the whole project.
