# 🛠️ Show Nomad Dockerfile

Action to display the FD.io Nomad executor Dockerfile on the self-hosted runner.

## Usage Example

Displays the Dockerfile used to build the executor container for debugging and monitoring purposes.

<!-- markdownlint-disable MD013 -->
```yaml
- name: "Show Nomad Dockerfile"
  uses: fdio/.github/.github/actions/show-nomad-dockerfile@main
```
<!-- markdownlint-enable MD013 -->

## Output

The action displays the following information:
- **Dockerfile Path**: `/scratch/docker-build/Dockerfile`
- **Dockerfile Content**: Complete contents of the Dockerfile if it exists

## Requirements/Dependencies

This action is designed to run on self-hosted Nomad runners and requires:

- Access to `/scratch/docker-build/Dockerfile` (the Dockerfile used to build the executor container)

The action will gracefully handle missing files and display appropriate fallback messages.