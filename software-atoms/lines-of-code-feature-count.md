# Lines of code != feature count

One of the team (not personal!) acomplishments I am most proud of is when the line count stays relatively the same as more features are added.



This is a fundamental example of how software should be built iteratively.

Make it work. Make it right. Make it fast.

When you shape a feature it is easy to get it right if you allow yourself more freedom on the aproach. Fast feedback, but sub optimal quality. With tests you can easily refactor.

Once it is done it is much, easier to find logical duplication, fake data structures or types, etc.



Let's take an example project:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>Linecount for a project over the period of 9 months</p></figcaption></figure>

The first thing you will notice is the steep fall of line count. This was done via moving to a monorepo and abstracting the shared components. In a sense the steep line was dublicated code even though it didn't always trivially look the same.

The more important part though is here:

![](<../.gitbook/assets/image (5) (1).png>)

The code goes up, but it also goes down.

This shows the continued effort of the team to keep things lean.

