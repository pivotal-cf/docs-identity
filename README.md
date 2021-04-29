# Single Sign-On (SSO) for VMware Tanzu Docs

This repo contains the documentation for Single Sign-On for VMware Tanzu, which enables users to
authenticate with an external identity provider rather than having to create a new account or re-enter credentials. Single Sign-On grants users centralized access to applications in various spaces, as well as to <%= vars.ops_manager %>, Apps Manager, and other Cloud Foundry components.

In this README:

- [Branches in this Content Repo](#branches-in-this-content-repo)
- [Releasing a New Minor Version](#releasing-a-new-minor-version)
- [Partials](#partials)
- [Contributing to Documentation](#contributing-to-documentation)
- [Publishing Docs](#publishing-docs)
- [Troubleshooting Markdown](#troubleshooting-markdown)
- [Style Guide](#style-guide)

### Branches in this Content Repo

| Branch name | Use for… | Publishes to… |
|-------------| ------|--------|
|**master** | This branch is on staging. ADD ALL NEW CONTENT  to this branch — if there's going to be 1.15 or a 2.0. | <a href="https://docs-staging.vmware.com/en/draft/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.15/documentation/GUID-index.html</a> |
|**1.14** | This branch contains the published documentation for the v1.14 release of SSO.  | https://docs-staging.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.14/documentation/GUID-index.html |
|**1.13** | **Do not update**. This branch is obsolete. | https://docs-staging.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.13/documentation/GUID-index.html |
|**1.12** | **Do not update**. This branch is obsolete. | https://docs-staging.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.12/documentation/GUID-index.html |
|**1.11** | **Do not update**. This branch is obsolete. | https://docs-staging.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.11/documentation/GUID-index.html |
|**1.10** | **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/p-identity/1-10/">https://docs.pivotal.io/p-identity/1-10/</a> |
|**1.9** |  **Do not update**. This branch is obsolete. | <a href="https://docs.pivotal.io/p-identity/1-9/">https://docs.pivotal.io/p-identity/1-9/</a>|
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

## Releasing a New Minor Version

Because **master** is the latest and greatest documentation, the process would be to cut a **x.x** branch
for the version that **master** was targeting during that time.

After this point, **master** will then be the target for the next version of this product.


## Partials

Cross-product partials for these docs are single sourced from the [Docs Partials](https://github.com/pivotal-cf/docs-partials) repository.


## Contributing to Documentation

If there is some documentation to add for an unreleased patch version of these docs, then create a branch off of the **live** branch
you intend to modify and create a pull request against that branch.
After the version that change is targeting is released, the pull request can be merged and will be live
the next time a documentation deployment occurs.

If the documentation is meant to be target several released versions,
then you will need to:
+ create a pull request for each individual minor version
+ or ask the technical writer to cherry-pick to particular branches/versions.

For instructions on how to create a pull request on a branch and instructions on how to create a
pull request using a fork, see
[Creating a PR](https://docs-wiki.sc2-04-pcf1-apps.oc.vmware.com/wiki/external/create-pr.html)
in the documentation team wiki.


## Publishing Docs

- [docworks](https://docworks.vmware.com/) is the main tool for managing docs used by writers.
- [docsdash](https://docsdash.vmware.com/) is a deployment UI which manages the promotion from
staging to pre-prod to production. The process below describes how to upload our docs to staging,
replacing the publication with the same version.

### Prepare Markdown Files

- Markdown files live in this repo.
- Images should live in an `images` directory at the same level and linked with a relative link.
- Each page requires an entry in [config/toc.md](config/toc.md) for the table of contents.
- Variables live in [config/template_variables.yml](config/template_variables.yml).

### In Docsdash

1. Wait about 1 minute for processing to complete after uploading.
2. Go to https://docsdash.vmware.com/deployment-stage

   There should be an entry with a blue link which says `Documentation` and points to staging.

### Promoting to Pre-Prod and Prod

**Prerequisite** Needs additional privileges - reach out to a manager on the docs team [#tanzu-docs](https://vmware.slack.com/archives/C055V2M0H) or ask a writer to do this step for you.

1. Go to Staging publications in docsdash  
  https://docsdash.vmware.com/deployment-stage

2. Select a publication (make sure it's the latest version)

3. Click "Deploy selected to Pre-Prod" and wait for the pop to turn green (refresh if necessary after about 10s)

4. Go to Pre-Prod list  
  https://docsdash.vmware.com/deployment-pre-prod

5. Select a publication

6. Click "Sign off for Release"

7. Wait for your username to show up in the "Signed off by" column

8. Select the publication again

9. Click "Deploy selected to Prod"


## Troubleshooting Markdown

| Problem | List displays as a paragraph |
|---------|-----------|
| Symptom:| Bulleted or numbered lists look fine on GitHub but display as a single paragraph in HTML.|
| Solution: | Add a blank line after the stem sentence and before the first item in the list.|

| Problem | List numbering is broken: every item is `1.` |
|---------|-----------|
| Symptom:| Each numbered item in a list is a `1.` instead of `1.`, `2.`, `3.`, etc|
| Solution: | Try removing any blank newlines within each step.|

| Problem | Code boxes not showing |
|---------|-----------|
| Symptom:| VMware publishing system doesn't accept code tags after the three back ticks.|
| Solution: | Make sure you're not using `shell` or `bash` or `console` or `yaml` after back ticks.|


## Style Guide

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
