# 🛠️ Show Nomad Attributes

Action to show the FD.io Nomad executor attributes inside a GitHub
action/workflow running on a self-hosted runner.

## Usage Example

Displays system and Nomad executor attributes for debugging and monitoring purposes.

### Basic Usage

<!-- markdownlint-disable MD013 -->
```yaml
- name: "Show Nomad Attributes"
  uses: fdio/.github/.github/actions/show-nomad-attributes@main
```
<!-- markdownlint-enable MD013 -->

### With Custom Delimiter

<!-- markdownlint-disable MD013 -->
```yaml
- name: "Show Nomad Attributes"
  uses: fdio/.github/.github/actions/show-nomad-attributes@main
  with:
    TUI_LINE: "=========================================="
```
<!-- markdownlint-enable MD013 -->

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `TUI_LINE` | Delimiter line for TUI output | No | `*******************************************************************` |

## Output

The action displays the following information:
- **OS Name and Version**: From `/etc/os-release`
- **Architecture**: System architecture (e.g., x86_64, arm64)
- **Nomad Client Name**: From `/scratch/nomad/nomad-client` file
- **Container ID**: Current container hostname

## Requirements/Dependencies

This action is designed to run on self-hosted Nomad runners and requires:

- Access to `/etc/os-release` for OS information
- Optional: Nomad client name file at `/scratch/nomad/nomad-client`

The action will gracefully handle missing files and display appropriate fallback messages.