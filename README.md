# EditRepo.yml
Copy the <a href="https://github.com/sap-ai/EditRepo.yml/blob/main/EditRepo.yml">yml</a> into your github workflow to make anyone able to edit your repo.(If needed github can close this project down)
```yaml
name: Version Build

on:
  push:
    branches: [ main ]

jobs:
  build-version:

    runs-on: ubuntu-latest

    steps:
    - name: Git checkout
      uses: actions/checkout@v2
      with:
        fetch-depth: '0'
    - name: git
      run: |
        git --version
        git config user.name "GitHub Actions Bot"
        git config user.email "<>"
        git status
        git tag
        git describe
        git merge --squash main
        git commit
