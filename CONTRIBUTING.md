# How to contribute to a DigitalBits project

Your contributions to the DigitalBits network will help improve the world’s financial
infrastructure, faster.

We want to make it as easy as possible to contribute changes that
help the DigitalBits network grow and thrive. There are a few guidelines that we
ask contributors to follow so that we can merge your changes quickly.

## Getting Started

* Make sure you have a [GitHub account](https://github.com/signup/free)
* Create a GitHub issue for your contribution, assuming one does not already exist.
  * Clearly describe the issue including steps to reproduce if it is a bug.
* Fork the repository on GitHub

### Minor Changes

#### Documentation

For small changes to comments and documentation, it is not
always necessary to create a new GitHub issue. In this case, it is
appropriate to start the first line of a commit with 'doc' instead of
an issue number.

## Finding things to work on

The first place to start is always looking over the current github issues for the project you are interested in contributing to. Issues marked with [help wanted](https://github.com/issues?q=is%3Aopen+is%3Aissue+user%3ADigitalBitsOrg+label%3A%22help+wanted%22) are usually pretty self contained and a good place to get started.

Digitalbits.io also uses these same GitHub issues to keep track of what we are working on. If you see any issues that are assigned to a particular person or have the `in progress` label, that means someone is currently working on that issue. The `orbit` label means we will likely be working on this issue in the next week or two. The `ready` label means that the issue is one we have prioritized and will be working on in our next orbit or two.

Of course, feel free to make your own issues if you think something needs to added or fixed.

## Making Changes

* Create a topic branch from where you want to base your work.
  * This is usually the master branch.
  * Please avoid working directly on the `master` branch.
* Make sure you have added the necessary tests for your changes and make sure all tests pass.

## Submitting Changes

* [Sign the Contributor License Agreement](https://developer.digitalbits.io/contributor.html)
* All content, comments, and pull requests must follow the [DigitalBits Community Guidelines](https://www.digitalbits.io/community-guidelines/).
* Push your changes to a topic branch in your fork of the repository.
* Submit a pull request to the [docs repository](https://github.com/xdbfoundation/docs) in the DigitalBits organization.
 * Include a descriptive [commit message](https://github.com/erlang/otp/wiki/Writing-good-commit-messages).
 * Changes contributed via pull request should focus on a single issue at a time.
 * Rebase your local changes against the master branch. Resolve any conflicts that arise.

At this point you're waiting on us. We like to at least comment on pull requests within three
business days (typically, one business day). We may suggest some changes, improvements or alternatives.

# Additional Resources
* [Contributor License Agreement](https://developer.digitalbits.io/contributor.html)


This document is inspired by:

* https://github.com/puppetlabs/puppet/blob/master/CONTRIBUTING.md
* https://github.com/thoughtbot/factory_girl_rails/blob/master/CONTRIBUTING.md
* https://github.com/rust-lang/rust/blob/master/CONTRIBUTING.md
