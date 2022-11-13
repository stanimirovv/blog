# Incremental Feature Delivery

## Synopsis <a href="#synopsis" id="synopsis"></a>

Decoupling features into chunks that can be merged daily or every 2 days ensures the code is integrated, progress is visible, interested parties can review the functionality and provide feedback.

Wrong development decisions, most tech debt and bugs can be found and fixed in advance.

Problem\
\
 <a href="#problem-hardbreak" id="problem-hardbreak"></a>
---------------------------------------------------------

Feature progress is slow, progress isn't clear. Long lived feature branches are a pain to integrate due to merge conflicts, code duplication, decisions taken by the developer which aren't optimal but would require time to fix remain and "Will be fixed later"

A lot of pressure is felt in the last few days of the sprint when everything needs to come together and work smoothly.

Even if everything is merged unless there is a very good integration test suite there will likely be bugs that the users will find.\
\


Solution\
\
 <a href="#solution-hardbreak" id="solution-hardbreak"></a>
-----------------------------------------------------------

The general strategy is to decouple the feature components until you are left with work that should take 1-2 days of work before it is merged.

This includes the review/refactoring, tests and merge time, so in reality the amount of new code that can be written isn't that much.(\~100-300lines/day from my experience, not that lines of code matter, but I can't think of a good measure metric)\
\


Below are two examples I've worked on recently to showcase examples for incremental feature development.\
\


The main thing is that work should be delivered every 1-2 days, the best strategy is the one that best fits the team.

Decoupling the features requires the developer to understand the problem deeply.

&#x20;

#### Use Case 1 - Top down approach <a href="#use-case-1-top-down-approach" id="use-case-1-top-down-approach"></a>

An api endpoint in a microservice accepts base64 encoded documents(doc, docx, pdf), and does data processing.

The api must also start supporting plain text.\
\


Top down approach:

* API Changes&#x20;
* Datastructure changes
* Business logic changes, tests (PR3, PR4)
* OpenAPI changes, logs

&#x20;

* PR1 Make the API changes - start supporting the new type of document, make a simple e2e test that validates that placeholder text is returned
* PR2 Work on the error handling, sync with the team if any new error types should be added, discuss any complex changes to the data types, add them to the project, add validation and error handling.
* PR3 Add the rest of the business logic - in the case there is a library that handles the text extraction, it needs to be extended to support the new type. Add tests.
* PR4 With the business logic from PR3 integrate it into the service. Make sure it works as expected and breaks gracefully.
* PR5 Add OpenAPI definitions to make the api "public". Check if there are any useful logs that could be added and haven't been added so far.

### Use Case 2 - Bottom up approach <a href="#use-case-2-bottom-up-approach" id="use-case-2-bottom-up-approach"></a>

A UI that has a an ellaborate "search form" needs to autocomplete Job Titles and Skills using the newly built autocomplete functionality by one of the DataScience micro services.\
\


Bottom up approach:

* Library changes
* Data Structure changes
* integrate into the existing business logic
* Add visual things
* Polish the library/integration code, check logs
* Polish the UI\
  \

* PR1 implements the API call in the client library. Make sure it behaves correctly, can be called, the authentication works, breaks gracefully
* PR2 add missing data structures, make sure the api is called on input change
* PR3 add a basic visualization to the list, updated on each change
* PR4 add logic to stop the flood towards the api&#x20;
* PR5 style the components, make sure on error the ui behaves gracefully

### Common pitfalls <a href="#common-pitfalls" id="common-pitfalls"></a>

The most common pitfall I’ve seen is that developers have a hard time decoupling the work if they don’t understand the problem they are solving well enough. This can be a multi layered problem:&#x20;

* unrefined User Stories/ Features
* lack of experience by the developer
* lack of focus due to working on multiple tasks at the same time

&#x20;

A good solution to these issues is proactive communication - if something is unclear/unrefined it should be refined ASAP and if unrefined tasks are common this should be discussed in the sprint retrospective.&#x20;

If the developer doesn’t have experience in something, narrowing down the unknowns to concrete questions and resolving them with a pair programming session can be a fast way to resolve this. (The developer needs to be prepared though - if there are no specific and ready questions the pair session won’t be particularly useful)
