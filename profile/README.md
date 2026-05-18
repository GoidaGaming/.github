# Welcome to GoidaGaming!

> This is work-in-progress basics about what to use and how to contribute. Changes may be applied later. Watch out for (work-in-progress) app notifications and/or DMs from elders on any major change to this doc.

You`ve been chosen to work with us since your birth. There are simple tooling and rules needed before you can start contributing to our brilliant code base.

## Dev environment

### Programs and IDEs

No version restrictions, just have these tools and that`s it.

* `VS Code` - Code development;
* `Docker` - Dev containerization and local staging;
* `DBeaver` or `Prisma Studio` - Database inspection;
* `Postman` - API testing;
* `Kleopatra` or similar - Commit signing and stuff;
* `Android Studio` - Mobile development;
* Anything that interacts with `git` (`VS Code` extensions, `shell` or whatever);
* Any `chromium` based browser + `Brave` (or similar) for tracking testing.

### Extensions and Code Style

Managed by `VS Code` profile. They should be the same across whole team. No exceptions. We might add new ones, but changes should be approved first.

Profile can be found in [this](https://github.com/GoidaGaming/.github) repo.

## Stack

Same as programs, no version restrictions. Using latest when possible, upgrading to latest when possible AND if nothing breaks. If backwards compatibility broken - test first, approve next, and only then use and deploy.

### Web

* `TypeScript` only;
* `NextJS` for frontend;
* `NestJS` for backend;
* `@goidagaming/data` - For database and cache:
  * `Prisma` used for database;
  * `Redis` client (not `ioredis`) for cache interactions.
* `MUI` for base components, `styled` for customization;
* `RTK` and `RTK Query` - Front-to-Back interactions;
* `turbo` for task automation and build caching;
* `pnpm` as package manager.

Preferably, you should use provided repo templates for new projects. If you need to add new sub project to your monorepo - copy contents from similar template, so it could be easily integrated into our automated ecosystem.

### Desktop

* Plain `ElectronJS` serving web page with `context` extension. Simple, stupid, yet effective.

### Mobile

`Kotlin` and whatever tools to connect it to our `API`. Exact stack will be reviewed later. Not enough time to make web working, and there`re already plans for mobile :\(

### Server

* `Docker` - Containerization and shi;
* `Traefik` - Proxy, web server, cert management and things like that;
* `GitHub Runners` - Self-hosted `CI/CD`;
* `GoidaGaming Web Deploy` - Work-in-progress `CI/CD` auto deploy solution;
* `GoidaGaming Remote Cache` - Work-in-progress `CI/CD` turbo remote cache solution;

...

Things like private docker/npm registers will be discussed and added later. Cope with that)

## Design code

`Material UI` (do not mistake for `MUI`) is what we should target. User friendly, simple, looks good.

`Figma` project will be added after first major release of any UI project.

## Contributions

### Existing projects

When working on new feature - always create a new `branch`, never push to `master` by hand, it may trigger `CI/CD` workflows. When new feature finished and ready to be tested - create `pull request`, wait til testing workflows succeed and assign reviewers. After successful review, `repo master` can merge your `branch` and/or create `release`. Everything else will happen automagically via `CI/CD pipeline` and shi like that.

### New projects

Create ticket or consult with elders about viability, then you can create repo from template. Wait `CI/CD` to succeed before cloning, or else it\`s a new round of CV applications for you! And that\`s it, everything ready for a new project. Same rules as `Existing projects` applied, btw. So keep in mind that `new feature = new branch`.
