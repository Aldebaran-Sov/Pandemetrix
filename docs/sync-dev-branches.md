# Sync Dev Branches Workflow

This GitHub Actions workflow automatically synchronizes all `dev/*` branches with the latest changes from the `main` branch whenever a pull request is merged into `main`.

## Overview

The workflow ensures that development branches stay up-to-date with the main branch, reducing merge conflicts and keeping feature branches current.

## Trigger

The workflow runs when:
- A pull request is **closed** (merged) into the `main` branch
- Only executes if the PR was actually merged (not just closed)

## Permissions

The workflow requires:
- `contents: write` - To checkout, fetch, and push to branches
- `pull-requests: write` - To access PR information

## Workflow Steps

### 1. Checkout Main Branch
- Checks out the `main` branch with full history (`fetch-depth: 0`)
- Uses the default `GITHUB_TOKEN` for authentication

### 2. Configure Git
- Sets up Git user identity for commits:
  - Email: `action@github.com`
  - Name: `GitHub Action`

### 3. Sync Dev Branches
The main synchronization logic:

#### Branch Discovery
- Fetches all remote branches
- Identifies all `dev/*` branches using pattern matching
- Skips if no dev branches exist

#### For Each Dev Branch
1. **Checkout**: Switches to the dev branch
2. **Update Check**: Compares with `origin/main` to count commits behind
3. **Skip if Current**: If already up-to-date, increments skip counter
4. **Merge**: Attempts to merge `origin/main` into the dev branch
5. **Push**: If merge succeeds, pushes the updated branch

#### Error Handling
- **Checkout Failures**: Logged and counted as failures
- **Merge Conflicts**: Automatically aborts merge and counts as failure
- **Push Failures**: Logged and counted as failures

## Exit Conditions

The workflow uses the following exit strategy:

- **Success (exit 0)**: If at least one branch was processed successfully (synchronized or already up-to-date)
- **Failure (exit 1)**: If all synchronization attempts failed
- **Success (exit 0)**: If no dev branches exist to process

## Output Summary

The workflow provides a detailed summary including:
- Number of branches successfully synchronized
- Number of branches already up-to-date
- Number of failed synchronizations
- Branch-by-branch progress logs

## Example Output

```
Branches to synchronize: dev/feature-auth dev/api-improvements

Checking dev/feature-auth...
Checkout dev/feature-auth successful
dev/feature-auth is 3 commits behind, synchronizing...
Merge successful for dev/feature-auth
dev/feature-auth synchronized and pushed

Checking dev/api-improvements...
Checkout dev/api-improvements successful
dev/api-improvements already up to date (no commits to synchronize)

Final summary:
    Synchronized: 1
    Already up to date: 1
    Failures: 0
Global synchronization successful
```

## Branch Naming Convention

This workflow operates on branches following the pattern:
- `dev/*` - Any branch starting with "dev/"

Examples:
- ✅ `dev/feature-auth`
- ✅ `dev/bug-fix-123`
- ✅ `dev/api-v2`
- ❌ `feature/auth` (doesn't match pattern)
- ❌ `hotfix/critical` (doesn't match pattern)

## Limitations

- **Merge Conflicts**: Branches with conflicts are skipped and marked as failed
- **Manual Resolution**: Conflicts require manual intervention
- **Branch Protection**: May fail if dev branches have protection rules requiring reviews
- **Token Permissions**: Limited by the permissions of `GITHUB_TOKEN`

## Best Practices

1. **Regular Merging**: Encourage frequent integration to minimize conflicts
2. **Clean Dev Branches**: Remove stale dev branches that are no longer needed
3. **Monitor Failures**: Check workflow logs for branches that consistently fail to sync
4. **Branch Hygiene**: Use consistent naming conventions for