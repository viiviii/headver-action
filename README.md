# headver-action

[HeadVer](https://github.com/line/headver) for git action.

The original source code is https://github.com/line/headver/blob/main/examples/bash.md


## Example


```
name: 'Using headver example'

on: workflow_dispatch

jobs:
  example:
    runs-on: ubuntu-latest
    steps:
      - name: '💫 Generate Version'
        id: version
        uses: viiviii/headver-action@v1
        with:
          head: 1
          build: 789
          suffix: qa

      - name: '🖨️ Output Summary'
        run: |
          echo "### Build version" >> $GITHUB_STEP_SUMMARY
          echo "${{ steps.version.outputs.version }}" >> $GITHUB_STEP_SUMMARY
```

The output of this example is as follows:

<img width="622" alt="image" src="https://github.com/viiviii/headver-action/assets/75404713/cf684c2b-b71b-4c43-8750-040c0a6afe80">
