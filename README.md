# Single Sign-On (SSO) for VMware Tanzu Docs

This repo contains the documentation for Single Sign-On for VMware Tanzu, which enables users to
authenticate with an external identity provider rather than having to create a new account or re-enter
credentials. Single Sign-On grants users centralized access to applications in various spaces,
as well as to Ops Manager, Apps Manager, and other Cloud Foundry components.

### Branch Management

| Branch name | Use for… | Publishes to… |
|-------------| ------|--------|
|**master** | This branch is on staging. ADD ALL NEW 2.0 (or 1.13) CONTENT to this branch. | <a href="https://docs-pcf-staging.cfapps.io/p-identity/1-n/">https://docs-pcf-staging.cfapps.io/p-identity/1-n/</a> |
|**master-pws** | This branch contains PWS-specific SSO content. The audience is plan administrators and developers; not operators. This content is stale.| <a href="https://docs.run.pivotal.io/sso/index.html">https://docs.run.pivotal.io/sso/</a>|
|**1.13** | This branch contains the published documentation for the v1.13 release of SSO.  | <a href="https://docs.pivotal.io/p-identity/1-13/">https://docs.pivotal.io/p-identity/1-13/</a> |
|**1.12** | This branch contains the published documentation for the v1.12 release of SSO.  | <a href="https://docs.pivotal.io/p-identity/1-12/">https://docs.pivotal.io/p-identity/1-12/</a> |
|**1.11** | This branch contains the published documentation for the v1.11 release of SSO.  | <a href="https://docs.pivotal.io/p-identity/1-11/">https://docs.pivotal.io/p-identity/1-11/</a> |
|**1.10** | This branch contains the published documentation for the v1.10 release of SSO.  | <a href="https://docs.pivotal.io/p-identity/1-10/">https://docs.pivotal.io/p-identity/1-10/</a> |
|**1.9** |  **Do not update**. This branch is obsolete.  | <a href="https://docs.pivotal.io/p-identity/1-9/">https://docs.pivotal.io/p-identity/1-9/</a> |
|**1.8** |  **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/p-identity/1-8/">https://docs.pivotal.io/p-identity/1-8/</a>|
|**1.7** |  **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/p-identity/1-7/">https://docs.pivotal.io/p-identity/1-7/</a>|
|**1.6** |  **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/p-identity/1-6/">https://docs.pivotal.io/p-identity/1-6/</a>|
|**1.5** |  **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/p-identity/1-5/">https://docs.pivotal.io/p-identity/1-5/</a>|
|**1.4** | **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/archives/docs-identity-1.4.pdf">https://docs.pivotal.io/archives/docs-identity-1.4.pdf</a>|
|**1.3** | **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/archives/docs-identity-1.3.pdf">https://docs.pivotal.io/archives/docs-identity-1.3.pdf</a>|
|**1.2** | **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/archives/docs-identity-1.2.pdf">https://docs.pivotal.io/archives/docs-identity-1.2.pdf</a>|
|**1.1** | **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/archives/docs-identity-1.1.pdf">https://docs.pivotal.io/archives/docs-identity-1.1.pdf</a>|
|**1.0** | **Do not update**. This branch is unpublished. The branch contains the  documentation for the EOL'd v1.0.10 release of SSO.|
| **master-on-April27** | A temporary snapshot of master to keep while we make large changes to the master branch. Please keep in sync with v1.6. |

### Books that Use This Repository

[docs-book-identity](https://github.com/pivotal-cf/docs-book-identity/)

[docs-book-runpivotal](https://github.com/pivotal-cf/docs-book-runpivotal/)

### Local Development
1. Clone https://github.com/pivotal-cf/docs-layout-repo
2. Clone https://github.com/pivotal-cf/docs-book-identity. Check out branch `edge` of this repo, verify that this branch has a config.yml that contains the newest SSO version properties. Create feature branch out of `edge` of to hold changes in sidebar structure and texts.
3. Clone https://github.com/pivotal-cf/docs-identity. Read the `README` of this repo to decide which branch to check out. Create feature branch out of the appropriate branch to hold changes in the actual documentation text content.
4. Get ruby 2.3.0 and follow steps on https://github.com/pivotal-cf/bookbinder
5. `cd docs-book-identity && bundle install`
6. To render the documentation with hotload changes: `cd docs-book-identity && bundle exec bookbinder watch` (Browse to localhost url in the output, for example, `localhost:4567/p-identity/1-n`).

### Development Workflow for APP SSO Team (for "docs-identity" & for a not-yet released SSO tile)
1. Check out `master` branch.
2. Create a feature branch with a branch name reflecting the purpose of the edit. E.g.: `git checkout -b update-product-version`
3. Commit onto the feature branch, and push the feature branch.
4. Create PR to request that the feature branch be merged into `master`, and include any appropriate contexts in the PR.
5. Docs team will review the PR and delete the feature branch once it is merged.

### Terminology

SSO has a lot of difficult and inconsistent terminology. Jane learned the following, working with Peter Chen in early July 2018.

| Term | Variations on Term | Notes |
|------|--------------------|-------|
| SSO Operator Dashboard | | Use this for the product name, put it in initial caps. |
| SSO Developer Dashboard | | Use this for the product name, put it in initial caps. |
| SSO Developer Dashboard | dashboard, developer dashboard, SSO dashboard, SSO UI | This is a dashboard with a UI that you log in to. There is a 1:1 between service instances and SSO developer dashboards. There is a many:1 between SSO developer dashboards and UAA identity zones|
| UAA identity zone | | Not sure of capitalization for this term. A subset of UAA. There is a 1:1 between plan and UAA Identity Zone. |
| UAA identity zone client | _many_ | There are two kinds of UAA Identity Zone client: admin client and non-admin clients.|
| UAAC vs UAAC CLI | User Account and Authentication Command Line Interface (UAAC) spell out first use | The UAAC is released, production quality that we discuss in the docs |
| UAA CLI | UAA-CLI  | The UAAC CLI is an experimental CLI ("incubating"). It is different from the UAAC, which is released. Don't discuss UAA CLI in the docs. |
| PCF app | | Use this for apps that are hosted on PCF. |
| externally hosted app | | Use this for apps that are hosted externally. |
| native apps |  | Native apps are mobile, desktop, or commandline apps. This is a different categorization from "PCF app vs externally hosted app". The most common native app is the mobile app. We wrote "native apps, such as mobile apps". Info from Tian, 2018.12.04 |
