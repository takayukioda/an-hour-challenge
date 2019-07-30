Vue GitHub
=====

Result
-----

commit: `262b3a5`

Couldn't make it.
Took time for a while to setup vue environment itself... and more over, all of those searches became waste when I found vue cli.

### Steps left (AFAIK)

- On click handling
- Run async function
- Actually send request with valid credentials and data

Objective
-----

Make a vue application that can post issue create request to GitHub, from scratch.

Using oauth is not in the scope of this objective. Use personal token for authorization.

Acceptance Criteria
-----

- [ ] Required
  - [ ] User can set GitHub personal token
  - [ ] Create GitHub issue when user inputs required information and click "make an issue" button
- [ ] Optional
  - [ ] Get a label list and let users to select from the list
  - [ ] Get a collaborator list and let users to select from the list
  - [ ] Get a milestone list and let users to select from the list if exists

Project setup
-----

```
yarn
```

### Compiles and hot-reloads for development

```
yarn run serve
```

### Compiles and minifies for production

```
yarn run build
```

### Run your tests

```
yarn run test
```

### Lints and fixes files

```
yarn run lint
```

### Customize configuration
  See [Configuration Reference](https://cli.vuejs.org/config/).
