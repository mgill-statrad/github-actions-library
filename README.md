# github-actions-library
Shared reusable workflows and action steps

# Reusable Terraform Release Workflow

This repository provides a reusable workflow for automating validation, tagging, archiving, and release of Terraform projects.

## Usage

You can call this workflow from another repository or workflow using `workflow_call`:

```yaml
jobs:
  call-terraform-release:
    uses: mgill-statrad/github-actions-library/.github/workflows/terraform.yml@main
    with:
      terraform_version: '1.5.0'
      terraform_directory: './terraform'
      archive_prefix: 'terraform'
      release_name: 'Terraform Release'
      release_body: |
        ## Custom Release Body
        ...
      tag_prefix: 'v'
```

## Inputs
- `terraform_version`: Version of Terraform to use (default: 1.5.0)
- `terraform_directory`: Directory containing Terraform files (default: ./terraform)
- `archive_prefix`: Prefix for release archive name (default: terraform)
- `release_name`: Name for the release (default: Terraform Release)
- `release_body`: Markdown body for the release notes
- `tag_prefix`: Prefix for git tag (default: v)

## Outputs
None

## Location
- `.github/workflows/terraform.yml`

For more details, see the header comment in the workflow file.
