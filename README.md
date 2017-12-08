# Guide to using Pivotal Single Sign-On

This is a guide to the Pivotal Single Sign-On service, which enables Pivotal Cloud Foundry users to
authenticate with an external identity provider rather than having to create a new account or re-enter credentials. Single Sign-On grants users centralized access to applications in various spaces, as well as to Ops Manager, Apps Manager, and other Cloud Foundry components.

<strong>Note:</strong> The <code>master</code> branch of this repository publishes to <a href ="https://docs.pivotal.io">PCF</a>, and the <code>master-pws</code> branch publishes to <a href="https://docs.run.pivotal.io">PWS</a>.

This doc repository is one of several doc repositories that go into a complete documentation set.

The contents here are structured as a topic repository intended to be compiled into a larger document with Bookbinder.

See the docs-book-cloudfoundry repo for the complete list of open source documentation repositories, as well as information about the publishing process.

### Branch Management

**master** - As of September 19, 2017. This branch is similar to the master-pws. What is its purpose?

**1.5** - branch for documentation for upcoming v1.5 release. As of September 19, 2017, this is staged at [https://docs-pcf-staging.cfapps.io/p-identity/1-5/](https://docs-pcf-staging.cfapps.io/p-identity/1-5/index.html).

**1.4** - branch for latest release documentation for v1.4 release. As of September 19, 2017, this is branch holds the most recent docs published at [https://docs.pivotal.io/p-identity/1-4](https://docs-pivotal.io/p-identity/1-4/index.html).

**1.6** – Don't touch this branch. It is an old branch that was used for the PCF v1.6 release.
          When SSO v1.6 is ready to document, we can build a new 1.6 from the 1.5 branch
          and rename the original to keep as an archive.  

### Books that Use This Repository

[docs-book-identity](https://github.com/pivotal-cf/docs-book-identity/blob/master/config.yml)

[docs-book-runpivotal](https://github.com/pivotal-cf/docs-book-runpivotal/blob/master/config.yml)
