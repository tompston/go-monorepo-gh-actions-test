# Example: Trigger Github Actions only on change in directory

Example which shows how to trigger github actions when a file in directory is is changed. 

This helps to fix the following problem: 

1. You have a monorepo which holds multiple projects
2. You want to do CI/CD for each project, but triggering builds for all projects on a push to branch x is not efficient, when only one of the projects has changed.

To fix this problem, you can specify in the workflow that it should only be triggered when a file in a specific directory has changed.

This means that one repo can hold multiple projects, and each project can have its own CI/CD workflow.

## Example

```yml
name: Run Service 1 On change in internal/first_service dir

on: 
  push:
    branches:
      - main  
    paths:
      - 'internal/first_service/**' # Trigger workflow only when a file in this directory has changed

# ... rest of workflow
```

