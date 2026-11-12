# Web service starter

A template for a new web service on Cloud Run, in Node.js: a deploy on each version tag
when a person approves it, with Workload Identity Federation from GitHub and Sentry for
errors. The service's own README is [README.md](../README.md): it is what a new app gets.

[Agents](https://github.com/alexec/Agents) makes a new app's repository from it with its
`make_app_repository` tool (starter `web-service`, or this repository by name). You can also
press **Use this template**, then fill the placeholders yourself.

## Placeholders

Each file names what the person chose with a placeholder. Agents fills them before the first
commit, so a new app never says one.

| Placeholder | What | Example |
| --- | --- | --- |
| `__APP_NAME__` | the app's name, as the person says it | `Tide Log` |
| `__SERVICE__` | the Cloud Run service | `tide-log` |
| `__GCP_PROJECT__` | the Google Cloud project | `tide-log-4821` |
| `__GCP_REGION__` | the Cloud Run region | `us-central1` |
| `__GITHUB_REPO__` | the new repository, `owner/name`; Agents fills it itself | `someone/tide-log` |

## The template's own files

`.starterignore` names the files that are this template's, not the app's: this README, its
CI (`.github/workflows/template.yml`) and `.github/template/`. Agents leaves them out of a
new app. The CI fills the placeholders with sample values (`.github/template/fill.py`),
checks the deploy, installs the service, starts it and asks it `/healthz`, so a change here
is checked here.

To make your own starter, fork this repository, change it and name your fork as the starter.
Agents takes the default branch each time, so a fix reaches the next new app at once.
