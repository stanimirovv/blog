# Mocking Private Functionality

😱 Mocking private functionality is bad design! Or is it ?

There are two schools of thought:

1. Private things should be mocked out - you are interested in testing a unit and must mock out everything
2. If you need to mock out something private this showcases bad design, therefore you need to refactor

🤔 It depends. On how you scope your private code.

⭐ Generally I am more and more against having lots of private functionality in classes. ⭐ Classes should be so small that no functionality that does something substantial should exist.

! If it exists it must be extracted into it's own class (or function or any container, really)

The extracted class should be scoped in a way that from the architecture perspective it will be usable only by the intended class.

🥰 With this setup you can test. 🥰 You have separated the concerns. 🥰 Have a more decoupled codebase.

But, that is just one way to do it. Strong arguments can be made against. Aren't you polluting the namespace with "fake" classes that shouldn't exist ?

Depends on scoping.
