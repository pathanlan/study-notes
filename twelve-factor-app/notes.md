# The Twelve Factor App

[URL](https://12factor.net/)

## Notes

* II. Dependencies
  * ❔ Dependency declaration vs dependency isolation - how does this look for us in C#/.Net land?
* III. Config
  * > An app’s config is *everything that is likely to vary between deploys* (staging, production, developer environments, etc).
  * > A litmus test for whether an app has all config correctly factored out of the code is whether the codebase could be made open source at any moment, without compromising any credentials.
  * Environment variables
    * > ...are never grouped together as “environments”, but instead are independently managed for each deploy.
    * ❔ How does this work in practice? It seems difficult to decouple env vars from environment groupings.
* VI. Processes
  * > The memory space or filesystem of the process can be used as a brief, single-transaction cache...The twelve-factor app never assumes that anything cached in memory or on disk will be available on a future request or job  – with many processes of each type running, chances are high that a future request will be served by a different process.
  * > Some web systems rely on “sticky sessions” – that is, caching user session data in memory of the app’s process and expecting future requests from the same visitor to be routed to the same process. Sticky sessions are a violation of twelve-factor and should never be used or relied upon. 
  * Sticky sessions 🤢