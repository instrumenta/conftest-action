# Conftest

A [GitHub Action](https://github.com/features/actions) for using [Conftest](https://github.com/instrumenta/conftest) in your workflows.

You can use the action as follows:

```yaml
on: push
name: Validate
jobs:
  conftest:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: test
      uses: instrumenta/conftest-action@master
      with:
        files: deployment.yaml
```

The Conftest Action has a small number of properties which map to the parameters for Conftest itself. These are
passed to the action using `with`, as demonstrated with `files` in the above example.

| Property | Default | Description |
| --- | --- | --- |
| files | - | *Required* which files to test |
| policy | policy | Where to find the policy folder or files |
| namespace | main | The Rego namespace to use for testing |
| output | stdout | How to format the output from Conftest (stdout, github, json or tap, check the full list [here](https://www.conftest.dev/options/#-output)) |


## Helm

Conftest also has a [Helm plugin](https://github.com/instrumenta/helm-conftest) which makes testing Helm charts easier, and
that plugin is also available as an Action.

You can use the action as follows:

```yaml
on: push
name: Validate
jobs:
  conftest:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: test
      uses: instrumenta/conftest-action/helm@master
      with:
        chart: mysql
```

The Conftest Helm Action has a small number of properties which map to the parameters for Conftest itself. These are
passed to the action using `with`, as demonstrated with `chart` in the above example.

| Property | Default | Description |
| --- | --- | --- |
| chart | - | *Required* which chart directory to test |
| policy | policy | Where to find the policy folder or files |
| namespace | main | The Rego namespace to use for testing |
| output | stdout | How to format the output from Conftest (stdout, github, json or tap, check the full list [here](https://www.conftest.dev/options/#-output)) |



