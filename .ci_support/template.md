# My Github Hirsch Index

[![Deploy](https://github.com/{{ repository }}/workflows/Deploy/badge.svg)](https://github.com/{{ repository }}/actions)

| Username    | Attributed Github Stars | Github Hirsch Index |
|-------------|------------------------:|------------------------:|
| [{{ username }}](https://github.com/{{ username }}) | {{ githubattributedstars }} :star: | {{ githubhirsch }} :zap: |

## Repositories 

| Repository | Attributed Github Stars | Total Github Stars |
|------------|------------------------:|-------------------:|
{% for package in package_lst -%}
{% if package[1] >= githubhirsch %}
| [**{{ package[0] }}**](https://github.com/{{ package[0] }}) | {{ package[1] }} :star: | ![GitHub Repo stars](https://img.shields.io/github/stars/{{ package[0] }}) |
{% else %}
| [{{ package[0] }}](https://github.com/{{ package[0] }}) | {{ package[1] }} :star: | ![GitHub Repo stars](https://img.shields.io/github/stars/{{ package[0] }}) |
{% endif %}
{% endfor %}

## Calculate your Github Hirsch Index

To calculate your Github Hirsch Index, simply fork this repository and set the environment variable `GH_TOKEN` as a [github action secret](https://docs.github.com/en/actions/reference/encrypted-secrets#creating-encrypted-secrets-for-a-repository):

```
GH_TOKEN = <your Github token which enables access to public_repo and read:org>
```

For the token the following permissions are required:
![Required Permissions](permissions.png)

After creating the environment variable `GH_TOKEN` trigger a new build on the master branch. 

If you have just forked the repo, you need to enable Github Actions for your fork by going to the `Actions` tab in the repository settings as well as allowing the Github Action to push to your fork to upload your newly calculated Github Hirsch Index.
