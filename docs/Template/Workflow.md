---
share: true
---

There is a lot of Github Actions here ! First, if you need information on what is a github action :
> [!cite] Definition
>  GitHub Actions makes it easy to automate all your software workflows, now with world-class CI/CD. Build, test, and deploy your code right from GitHub. Make code reviews, branch management, and issue triaging work the way you want.[^1]

I will explain everything, don't panik. As you can see, here, the github actions (~ the workflow) are used to build Obsidian To Mkdocs (Or Mkdocs Obsidian Publisher) using file in your repo. 

## Obsidian Mkdocs Publisher
### On push
The main workflow is in `ci.yml` . **It needs a push event where the commit name starts with `[PUBLISHER]`**. After that, it will scan the repository and try to find modified file (since the last commit). After find these file, it will convert it using obs2mk, and build the mkdocs site. 

## Manual run

You can also run manually the convertor using `Publisher Manual` (in the `manual_run.yml`).

> [!info] Tutorial to manually trigger the workflow using Github.com
> 1. First, go to *Actions*
> 2. You will see the list of the actions on your repository. Click on **publisher manual**.
> 3. Click on **run workflow** 
> 4. The run ask you for the file(s) you want to convert. You can convert multiple files using a [glob pattern](https://en.wikipedia.org/wiki/Glob_(programming)), like a folder or commune name. Each markdown file found will be converted by `obs2mk`. 
> ![[../assets/img/demo.gif]]

Note that you can also trigger the workflow using [Github CLI](https://cli.github.com/) using `gh workflow run manual_run.yml file=your_file`

If you want to have the last message with your mkdocs page, you need to edit the `.github/env.txt` with the link to your page. 

## Other workflow
It, also, exists :
- A workflow based on push where the name **doesn't startswith `[Publisher]`**, that build the mkdocs page (in case you manually edit a file, the overrides...)
- A workflow running each 24h to update `requirements.txt` (and you can also force update). I created it because the Github Cache needs a fixed version on requirements, but it happens regulary that I update some plugins or update in Material Mkdocs. So, this workflow will **only** change the `requirements.txt` if it founds an update.


> [!info] About workflow run
> If you use the workflows (every workflow) on a **private** repository, you needs to know that you have *only* 2000 minutes (3000 with pro account) of workflow run. 
> - Mkdocs Build takes around ~1min
> - Publisher actions takes also ~2min if changes were made 
> - Updating requirements (each 24 hours) take ~30s
>
> Note that Mkdocs actions will don't run if you use the publisher actions. Also, the actions will only run on the `main` or `master` branch. 
>
> Finally, you can run ~1000 blog's build by month (3000 for pro), so it's around 41 build by day.
> Note : The pip cache will normally accelerate the process, so Publisher action must take more than 1min-1min30 than two for little building.

[^1]: Thanks to [official website](https://github.com/features/actions)