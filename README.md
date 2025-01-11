# ZapTests Tool GitHub Action

This action runs API tests, version comparison, stress testing, assertion testing using a custom API testing tool which not only integrates with your CI/CD pipeline but also generates descriptive reports

## Inputs

### `runType`
**Required**: Type of test to run.

### `baselineEnv`
**Optional**: Baseline Env.

### `undertestEnv`
**Optional**: Undertest Env.

### `testEnv`
**Optional**: Test env.

### `runSettingsLocation`
**Required**: Runsettings json file path.

### `testsuitsLocation`
**Required**: Location of test suits.

### `outputLocation`
**Required**: Output folder to save the reports.

## Usage

```yaml
jobs:
  run-api-tests:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v3
      
      - name: Run API Tests
        uses: moonshrine/zaptests@v1
        with:
          runType: 'ComparisonTest'
          baselineEnv: 'BETA'
          undertestEnv: 'PROD'
          testEnv: 'PROD'
          runSettingsLocation: ''
          testsuitsLocation: ''
          outputLocation: ''
