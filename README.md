# gha-get-ref

Will retrieve the acting ref name regardless of trigger

### Usage

```yaml
name: GHA Runner

on:
  - push
  - pull_request
  - create
  - delete

jobs:
  playground:
    runs-on: ubuntu-latest
    name: GHA Runner
    steps:
      - name: Get Ref
        id: get_ref
        uses: dmsi-io/gha-get-ref@v1

      - name: Print Ref
        run: echo "${{ steps.get_ref.outputs.ref_name }}"
```

### Outputs

#### Ref Name

The only output and primary purpose of this action is the ref name.

```yaml
- name: Get Ref
  uses: dmsi-io/gha-get-ref@v1
  id: get_ref

- name: Print Ref Name
  run: echo ${{ steps.get_ref.outputs.ref_name }}
```
