# Single Sign-On (SSO) for VMware Tanzu Application Service Docs

This repo contains the documentation for Single Sign-On for VMware Tanzu Application Service, which enables users to
authenticate with an external identity provider rather than having to create a new account or re-enter
credentials. Single Sign-On grants users centralized access to applications in various spaces,
as well as to Ops Manager, Apps Manager, and other Cloud Foundry components.

In this README:

- [Single Sign-On (SSO) for VMware Tanzu Application Service Docs](#single-sign-on-sso-for-vmware-tanzu-application-service-docs)
    - [Branches](#branches)
  - [Releasing a new minor version](#releasing-a-new-minor-version)
  - [Partials](#partials)
  - [Contributing to documentation](#contributing-to-documentation)
  - [Publishing docs](#publishing-docs)
    - [Prepare Markdown files](#prepare-markdown-files)
    - [In Docsdash](#in-docsdash)
    - [Promoting to pre-prod and prod](#promoting-to-pre-prod-and-prod)
  - [Troubleshooting Markdown](#troubleshooting-markdown)
  - [Style guide](#style-guide)

### Branches

| Branch name | Use for… | Publishes to… |
|-------------| ------|--------|
|**main** | This branch is on staging. ADD ALL NEW CONTENT  to this branch — if there's going to be 1.15 or a 2.0. | https://docs-staging.vmware.com/en/draft/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.15/sso/GUID-index.html |
|**1.14** | This branch contains the published documentation for the v1.14 release of SSO.  | On staging at https://docs-staging.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.14/sso/GUID-index.html and on prod at https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.14/sso/GUID-index.html |
|**1.13** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.13/single-sign-on-for-tas-1-13.pdf |
|**1.12** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-Service/1.12/single-sign-on-for-tas-1-12.pdf |
|**1.11** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-service/1.11/Single-Sign-On-VMware-Tanzu-Application-service-1-11.pdf |
|**1.10** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-service/1.10/Single-Sign-On-VMware-Tanzu-Application-service-1-10.pdf |
|**1.9** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-service/1.9/Single-Sign-On-VMware-Tanzu-Application-service-1-9.pdf |
|**1.8** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-service/1.8/Single-Sign-On-VMware-Tanzu-Application-service-1-8.pdf |
|**1.7** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-service/1.7/Single-Sign-On-VMware-Tanzu-Application-service-1-7.pdf |
|**1.6** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-service/1.6/Single-Sign-On-VMware-Tanzu-Application-service-1-6.pdf |
|**1.5** | **Do not update**. This branch is obsolete. | https://docs.vmware.com/en/Single-Sign-On-for-VMware-Tanzu-Application-service/1.5/Single-Sign-On-VMware-Tanzu-Application-service-1-5.pdf |
|**1.4** | **Do not update**. This branch is obsolete. | https://docs.pivotal.io/archives/docs-identity-1.4.pdf |
|**1.3** | **Do not update**. This branch is obsolete. | https://docs.pivotal.io/archives/docs-identity-1.3.pdf |
|**1.2** | **Do not update**. This branch is obsolete. | https://docs.pivotal.io/archives/docs-identity-1.2.pdf |
|**1.1** | **Do not update**. This branch is obsolete. | https://docs.pivotal.io/archives/docs-identity-1.1.pdf |
|**1.0** | **Do not update**. This branch is unpublished. The branch contains the  documentation for the EOL'd v1.0.10 release of SSO.|
| **master-on-April27** | A temporary snapshot of master to keep while we make large changes to the master branch. Please keep in sync with v1.6. |

## Releasing a new minor version

Because **main** is the latest and greatest documentation, the process would be to cut a **x.x** branch
for the version that **main** was targeting during that time.

After this point, **main** will then be the target for the next version of this product.


## Partials

Cross-product partials for these docs are single sourced from the [Docs Partials](https://github.com/pivotal-cf/docs-partials) repository.


## Contributing to documentation

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


## Publishing docs

- [docworks](https://docworks.vmware.com/) is the main tool for managing docs used by writers.
- [docsdash](https://docsdash.vmware.com/) is a deployment UI which manages the promotion from
staging to pre-prod to production. The process below describes how to upload our docs to staging,
replacing the publication with the same version.

### Prepare Markdown files

- Markdown files live in this repo.
- Images should live in an `images` directory at the same level and linked with a relative link.
- Each page requires an entry in [config/toc.md](config/toc.md) for the table of contents.
- Variables live in [config/template_variables.yml](config/template_variables.yml).

### In Docsdash

1. Wait about 1 minute for processing to complete after uploading.
2. Go to https://docsdash.vmware.com/deployment-stage

   There should be an entry with a blue link which says `Documentation` and points to staging.

### Promoting to pre-prod and prod

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


## Style guide

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
