# skip-duplicate-actions-demo


```yml
jobs:
  skip:
    runs-on: ubuntu-latest
    outputs:
      should_skip: ${{ steps.skip_check.outputs.should_skip }}
    steps:
      - id: skip_check
        uses: fkirc/skip-duplicate-actions@v5
        with:
          cancel_others: 'true'
          skip_after_successful_duplicate: 'false'
          paths_ignore: '["**.md", ".github/**"]'
```