# Roadie repository for github templates

## Issue templates

in the `ISSUE_TEMPLATE/` directory there are templates that show up each time someone creates a new issue. They have to be copied to any new repository that is being created to work there.

## Workflows templates

in the `workflow-templates/` directory there are templates that enable scaffolding from them when adding a new workflow to the repository through github web gui.

## Workflow syncing

If there is a need to update any file in all of the plugin repositories at once (workflow, issue template, configuration), you can do it by the `workflow-sync` workflow in this repository. It runs when commit with message `workflow-sync` is merged to main branch. It copies files mentioned in the `WORKFLOW_FILES` variable (format is `<sourceFile>=<destinationFile>`, more on this is documented [here](https://github.com/varunsridharan/action-github-workflow-sync#workflow_files-configuration-examples)) to all of the repositories listed in the `REPOSITORIES` bariable. Example below: 

```yaml
  REPOSITORIES: |
    roadieHQ/backstage-plugin-aws-auth
    roadieHQ/backstage-plugin-aws-lambda
  WORKFLOW_FILES: |
    workflows-to-sync/publish.yml=.github/workflows/publish.yml
```

## Links

- [Backstage](https://backstage.io)
- Get hosted, managed Backstage for your company: https://roadie.io
