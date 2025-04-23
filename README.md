Step by step instructions for setting up a angular application using dynamic federation

# Guide based on NX docs: [dynamic module federation with angular](https://nx.dev/recipes/angular/dynamic-module-federation-with-angular)

## 1. Create monorepo

```
$ pnpx create-nx-workspace@latest angular-module-federation --preset=apps
```

Next select Azure Devops as CI server

## 2. Add angular support to Nx Workspace using the NX plugin for angular

```
$ pnpx nx add @nx/angular
```

## 3. Create the host dashboard application for the micro-frontends

```
$ nx g @nx/angular:host apps/dashboard --prefix=ng-mf
```

## 4. Create a login app as a remote application

```
$ nx g @nx/angular:remote apps/login --prefix=ng-mf --host=dashboard
```

## 5. Create a shared user data-access library

```
$ nx g @nx/angular:lib libs/shared/data-access-user

```

## 6. create a user service in user data-access library

```
$ nx g @nx/angular:service user --project=data-access-user
```

To run both the host and the remote

```
$ nx run login:serve
$ nx serve dashboard --devRemotes=login
```
