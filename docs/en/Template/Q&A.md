---
share: true
---

## 1. Private repository

As I authorize this repo to be a template, it allows you to create a private repository!

> [!Note]
> Fork doesn't allow you to create a private repo, that's why you must use the template._

## 2. Update the template

Using a template (in place of fork) prevent to get the update I do sometimes. So, to keep an eye on it, you need to create a **branch** based on the template. 

In the cloned folder, (in your blog) do : 
```git
git remote add Template git@github.com:Mara-Li/obsidian-mkdocs-publisher-template.git
git fetch Template
git checkout -b template Template/main
```
After, to get the update : 
```git
git checkout template
git pull
```

You can merge the branch, or just get the updated file with the checkout command : 
```git
git checkout main
git checkout template path/file/youwant 
```
Don't forget to commit and push!

