# Terraform Training Module

This Terraform module uses [Release Please](https://github.com/googleapis/release-please) for automated versioning and release management.

## Release Process

### Automated Releases

Release Please automatically creates pull requests when commits follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

- **feat**: Creates a minor version bump
- **fix**: Creates a patch version bump
- **feat!** or **fix!**: Creates a major version bump (breaking change)

### Setup Requirements

1. Ensure your repository has a GitHub Actions workflow configured (`.github/workflows/release-please.yml` is included)
2. The workflow will automatically trigger on pushes to the `main` branch
3. Release Please will create a pull request with updated versions

### Configuration Files

- **release-please-config.json**: Main configuration file for Release Please
- **.release-please-manifest.json**: Tracks the current version of your module
- **package.json**: Contains the dev dependency for Release Please

### Making Releases

1. Create a commit with conventional commit messages (e.g., `feat: add new resource`)
2. Push to `main` branch
3. Release Please will automatically create a release PR
4. Merge the release PR to trigger an automated release on GitHub

### Conventional Commit Examples

```bash
# Feature commit (minor bump)
git commit -m "feat: add new data source"

# Bug fix commit (patch bump)
git commit -m "fix: correct resource configuration"

# Breaking change (major bump)
git commit -m "feat!: restructure module inputs"

# With scope
git commit -m "feat(aws): add support for new region"
```

## Local Development

To install dependencies and use Release Please locally:

```bash
npm install
npx release-please --help
```

## Resources

- [Release Please Documentation](https://github.com/googleapis/release-please)
- [Conventional Commits](https://www.conventionalcommits.org/)

