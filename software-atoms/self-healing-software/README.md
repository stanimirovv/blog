# Self Healing Software

Self healing software is gaining a lot of popularity.\
\


The pitch is: "Imagine the system detects and fixes errors in itself, therefore you don't need to worry about your environments, just about developing features"

It may sound too good to be true because it is.\
\


Let me elaborate.

&#x20;

Self healing works, for the most part, on several levels:

* Hardware - when a node goes bad, redeploy the software/data on a healthy one.
* System - when a container goes bad, redeploy it to a different pod. Or, when your app's process dies, retrigger it.

&#x20;

There are a lot of different solutions for Hardware and System.

From a developer's point of view you primarily need to worry a bit about the System.

If you are using one of the big commercial clouds (Amazon, Google, Azure) chances are by design the service you are using will restart itself if the master process dies or if the health check endpoint returns an error.\
\


There is one major issue that isn't solved easily (if at all) by self healing software and that is the application level errors.\
\


Don't get me wrong - it can work, but very situationally and mostly the situations in which it works are significantly less error prone than ones in which it doesn't work.\
\


Assume you have deployed a broken version. What would you do ? Rollback right ? That way the system is affected negatively for the least amount of time.

And the machine can do that as long as it can detect the issues, right ? Yes, it can.\
\


Even though the above scenario, let me give a few examples which will hopefully prove that this is dangerous and should be avoided.

1. What if the rollbacked version is also broken ? Imagine 2 bugs (releases) have slipped in. Until when should you rollback ?
2. What if the detected issue is in a non critical part of the software yet the previous version has mission critical changes ?
3. What if there are incompatible changes between releases ? Your consumers may be expecting REST but you may be serving RPC
4. What if there are incompatible schema changes ? Are you going to rollback the database too ? Isn't that dangerous?&#x20;

\
\


The list can go on, the point is there are many edge cases where automatic rollback is a risky idea.

&#x20;

So what can we do ?

Preventive design. Use types, write tests, think about the edge cases, make sure there are clear logs and the errors are handled. The usual "high quality software" stuff.
