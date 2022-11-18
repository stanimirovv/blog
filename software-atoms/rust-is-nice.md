# Rust is nice

I decided that I will dedicate a few months to Rust.

Golang's heavy, non functional syntax and lots of runtime errors never made me want to work extensively in the technology.

Oddly enough I have golang code still in prod to this day since 2014 just a few years after I started my professional career.

I digress.

First impressions after doing a few tiny apps like minigrep from the book and a partial Notes CRUD API I've found some gaps in my knowedge:

* Since you can't have integration tests in a binary crate most "Service" crates or crates that contain daemons should be a combination of binary + library to ensure you can do integration tests.
* I actually like the mechanism for testing private functions. It is dirty, yes, but if you will go down this path you shouldn't expect a clean solution.
* The way you build up module chains is unusual, or at least less straightforward than JS/Python.

That being said the journey is super enjoyable.

The entire Rust phylosophy is about building really roboust code.

I love the compiler's warnings for skipped errors, I really love the closure and iterator experiance in rust.

Don't get me wrong - Node is much more straightforward and low overhead, but I really really really see a lot of potential in Rust.

I am not turning this blog a rust brain dump, but I would expect the next posts will cover my Rust journey.
