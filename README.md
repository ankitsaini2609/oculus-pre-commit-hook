# oculus-pre-commit-hook

### Pre-Commit
1. Install pre-commit from https://pre-commit.com/#install
2. Create a `.pre-commit-config.yaml` file at the root of your repository with the following content:
```
- repo: https://github.com/ankitsaini2609/oculus-pre-commit-hook
  rev: master
  hooks:
    - id: gitleaks
```
3. Install with `pre-commit install`
4. Now you're all set!
```
➜ git commit -m "commit containing a secret"
Scanning for hardcoded credentials.................................................Failed
```
Note: to disable the gitleaks pre-commit hook you can prepend `SKIP=gitleaks` to the commit command
and it will skip running gitleaks. You can also use --no-verify which will skip the whole pre-commit.
```
➜ SKIP=gitleaks git commit -m "skipping gitleaks check"
Scanning for hardcoded credentials................................................Skipped
```
