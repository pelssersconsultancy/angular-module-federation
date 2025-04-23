Step by step instructions for setting up a angular application using dynamic federation

# Guide based on [NX docs: dynamic module federation with angular](https://nx.dev/recipes/angular/dynamic-module-federation-with-angular)

## 1. Create monorepo

```
$ pnpx create-nx-workspace@latest angular-module-federation --preset=apps
```

Next select Azure Devops as CI server

## 2. Add angular support to Nx Workspace using the NX plugin for angular

```
$ pnpx nx add @nx/angular
```
