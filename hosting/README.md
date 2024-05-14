# Hosting Helm chart private repositories in GitHub

## Prerequisites
- A Github account has been added to spartan Github Organization.
- Token has been generated following [Creating a personal access token for the command line](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) guidelines.

## Add spartan chart repository to your local

Since this repository is treated as spartan private repository, we need to add this chart repository to interact with any private chart located in private charts directory

```bash
$ helm repo add spartan https://<your-token>@raw.githubusercontent.com/<github-org>/infra-helm/master/hosting
```

## Store private chart to chart repository 

(*This step can be executed manually on GitHub Actions by creating a release.*)

The new private chart in this chart repository must be packaged and versioned corretly (following [SemVer 2](https://semver.org) guidelines)

```bash
$ cd hosting
$ helm package ../charts/spartan
```

Regenerate the index to completely rebuild the `index.yaml` file from scratch, including the charts that it finds locally. Ensure that the new chart has been indexed successfully.

```bash
$ cd hosting
$ helm repo index . --merge index.yaml
```


## References

- [Hosting HELM chart private repositories in GitHub and GitLab](https://www.goodwith.tech/blog/hosting-helm-chart-private-repository-in-github-and-gitlab#github)