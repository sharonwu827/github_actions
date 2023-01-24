# Github Action

Automate, customize, and execute your software development workflows right in your repository with GitHub Actions. You can discover, create, and share actions to perform any job you'd like, including CI/CD, and combine actions in a completely customized workflow. 
Github workflow are written in the YAML format.

1. In your repository, create the .github/workflows/ directory to store your workflow files.

2. In the .github/workflows/ directory, create a new yaml file.

```yaml
# Optional - The name of the workflow as it will appear in the "Actions" tab of the GitHub repository.
name: Shell Commands

# Specifies the trigger for this workflow
# example uses the push event, so a workflow run is triggered every time someone pushes a change to the repo or merges a pull request. 
on: [push]

# Groups together all the jobs that run in this workflow
jobs:
  # Defines a job name
  # The below child keys will define properties of the job.
  run-shell-command:
    runs-on: ubuntu-latest
    # Groups together all the steps that run in the job. 
    # Each item nested under this section is a separate action or shell script.
    steps:
      - name: echo a string
        run: echo "Hello World"
      - name: multiline script
        run: |
          node -v
          npm -v
```

3. Commit and push.


####Appendix:
- https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions
- [Workflow syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#using-a-specific-shell)