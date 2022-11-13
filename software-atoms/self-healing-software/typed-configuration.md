# Typed Configuration

I've been down the configuration rabbithole.

I’ve noticed that most tools in the JS eco system (prettier, jest, eslint, etc) amongst other env formats support the config to be kept inside javascript files. (They basically support .js/.json and inside package.json)

I decided to test out how much benefits we can get if we store the (again, non secret) configuration per environment in the code.

I created a configuration type and for illustration a factory that returns the environment’s contents based on input.

![](<../../.gitbook/assets/image (10).png>)

Then I created 2 configuration files:

![](<../../.gitbook/assets/image (3) (1).png>)

Since the exported variables were typed I got typehints and autocomplete where applicable.

The type errors are caught inside the editor and will be displayed when you try to run the app:

![](<../../.gitbook/assets/image (4) (1).png>)

You can use additional types that will let you get a lot more out of the compiler, such as setting the range value of integers.

You can [look here ](https://millsp.github.io/ts-toolbelt/)for inspiration for extra types.

Not sure how I feel about this. Further research required.
