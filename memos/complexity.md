# Complexity

We reduce complexity by introducing automation and process. Automation and process offer less risk and less cognitive load.

Complexity can’t be measured precisely. It is a relative, sometimes opinionated metric. What realistically you can build is an intuition that can tell you if something is complex or not.

You can’t normalize complexity - there isn’t a specific number or scale you can use that is universal.

Some very basic aspects of complexity, such as the [cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic\_complexity) can be measured, but complexity, on a larger scale can not.

We need to agree that code is costly. Complexity for code that doesn’t exist is none existent.

When you have code you have complexity.

This means that you should avoid writing code and rediscovering the wheel whenever possible.

Do not misunderstand - this doesn’t invite you to write unmaintainable code because it is less lines of code. The idea is to reuse and extend existing functionality and systems instead of writing code. If possible avoid writing new code.

One of the most intuitive and natural ways to look at complexity is “Does X fit in my head ?”. There is a different granularity to this. For example a single flow should fit in our head. A flow may include several systems. But each of the involved systems should also fit in your head.

The second there is a detail if the given granularity that you can’t remember or grasp doesn't fit in your head - this is a strong implication that the complexity is high and a split or refactoring should be made.

**Familiarity** does **not** mean **simplicity**.&#x20;

Familiarity is a temporary, in the moment knowledge. It can be transferred in the form of documentation, but this treats the symptom, not the cause - the complexity will remain. You may have docs to help you but you need to maintain them too and if you don’t they work against you.

Try to distinguish between familiarity and simplicity. An exercise you can do is to imagine you do not know absolutely anything about the system and you gain knowledge only by reading the code.

If the code is readable and simple you should understand the structure and implementation with relative ease. If it is complicated you will have to “think hard”.

Combining those concepts we can derive the following principle - When you open a non familiar piece of the code base it should fit in your head just by reading the code. If it doesn’t you should consider refactoring it.

Contextual consistency leads to simplicity - try to have less different types of objects in your architecture and implementation. For example use a single pattern for Database access, regardless if it is repository, active record, DAO, etc. When you have contextual simplicity the main difference will be the data.

Lastly, not all complexity is created equal. We can do a simple binary classification - complexity can be accidental and essential.

Accidental complexity is what these patterns most deal with as it is parts of the system that can be improved, refactored, etc.

Every project has essential complexity to it - complexity that if reduced will also reduce the value of the component. Reducing essential complexity is usually damages the project.

Distinguishing between both types of complexity is crucial when attempting to improve a system.
