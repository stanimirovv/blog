# Stabilizing Tests without fixing them

If you have the time fix your tests!

Now with that out of the way:

1. Run the tests sequentially
2. Retry the tests up to two times with a few seconds worth of pause

These two things are going to cover the most common reasons for flaky tests which are race conditions and lacking enough isolation.
