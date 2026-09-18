# Security

## Please do not open a public issue

A security problem posted as an issue is a problem everyone knows about before
there is a fix, including whoever would use it. Send it privately instead.

**nakkaankarao7@gmail.com**

Put "Nakka security" in the subject so it is not missed.

## What helps

- What the problem is, and what someone could do with it
- The steps to reproduce it, as short as you can make them
- Which version of Nakka, and which editor and operating system
- Whether you have told anyone else, and whether you plan to publish

You will get a reply. If the problem is real, you will be told when a fix is
out, and credited in the changelog unless you would rather not be.

## What is worth reporting

Nakka runs commands and edits files on your machine, so the things that matter
most are the ones that get round the part deciding whether it may:

- A command that runs without the permission prompt it should have raised
- A way past Plan mode's read-only rule
- A file read or written outside the workspace without asking
- Anything that sends your code, your keys or your settings somewhere other
  than the model provider you configured
- An API key appearing in a log, an error message or the transcript

## Supported versions

The current release on the marketplace. Fixes go into the next release rather
than into older versions.
