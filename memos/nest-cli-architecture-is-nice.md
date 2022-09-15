# nest-cli architecture is nide

The nest-cli repository has a very interesting implementation of the command pattern.\
(Repo: [![](https://github.githubassets.com/favicon.ico)](https://github.com/nestjs/nest-cli\)))

Useful Urls on the command pattern:

* [![](https://en.wikipedia.org/static/favicon/wikipedia.ico)Command pattern](https://en.wikipedia.org/wiki/Command\_pattern)
* [![](https://refactoring.guru/favicon.png)Command](https://refactoring.guru/design-patterns/command)

the gist about the command pattern is instead of executing a function you create an object which contains the arguments and execution code and has a method that will trigger it.\
The method can be called go/run/execute, etc.

The main benefit is that **what** needs to be executed is decoupled from **when** and **how**.

This is super useful - you can execute the command in another thread/worker, even another service (then it is likely a remote command though).\
The command can be generated on one layer of the app and executed in another.\
It is easy to build undo/redo and a "Transaction queue" if commands are implemented.

There is something quite uncommon in the command pattern implementation in the nest-cli though.\
Upon reviewing the source code it can be seen that the command itself is further decoupled into two parts:\
the **command** and the **action**. This is weird because usually the command consists of the arguments and the code that needs to be executed.

Splitting the command and the action means that double the amount of classes is generated.

Why though ?

I see two main reasons why this can be useful in the specific case of nest-cli.

1. The command itself handles and transforms the arguments therefore it is on the I/O layer which means that the business logic must be seperated if good seperation of concerns must be kept.
2. The action itself is a stateless (but not pure) class - meaning that it is easier to test.

What are your thoughts ? What benefits and drawbacks do you see in the nest-cli implementation ?
