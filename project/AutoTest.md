# AutoTest

AutoTest is a mechanism for validating your project deliverables. It uses _exactly_ the same mechanism to validate your code as most industrial teams use: automated testing. In our case we are using the [Mocha Test Environment](https://mochajs.org/) with [Chai Expectations](http://chaijs.com/api/bdd/) for unit tests and [IcedFrisby](https://www.npmjs.com/package/icedfrisby) for integration tests. Automation is a cornerstone of continuous integration practices which enable teams to quickly and confidently evolve their software systems while retaining trust in its operability.

While we will evaluate your code with a private suite, you should also create a personal suite to validate your code yourself.

### Personal Suite

The personal suite exists for three main purposes: 

* To provide a way for you to ensure your code passes the tests _you_ think are important from the deliverable specification.

* To provide a way for you to debug your code in a repeatable way.

* To enable you to test your deliverable repeatedly without incurring the rate limiting mechanism of the private test suite.

### Private Suite

The private suite exists for one purpose:

* To comprehensively validate the functionality of your system. 

The private suite will contain dozens of tests that will test both regular and exceptional behaviours. The private suite has two levels; in the first level we will execute your code with the dataset we gave you. In the second level we will use a new dataset to ensure you have not hard-coded shortcuts into your solution to pass the suite with the provided data set. You will get much more feedback about the first level tests than the second level tests.

### Testing Your Own Code

The private suites is an *integration* suite; that is they test your code only from the public InsightFacade and REST endpoints provided by your app. While you can create integration tests with your personal suite, you can also create unit tests. Unit tests will be much faster and easier for you to diagnose incorrect behaviours in your code. 

Unit tests are also the best way to run your system without invoking the whole REST server and invoking your system with curl. If you just want to test one specific method or class, this is the way to do it.

Learning how to write effective test cases takes time and practice. It is best to think about both common cases, so you can ensure your code works correctly, and edge cases, so you can make sure your code handles failures correctly and gracefully. You can be sure that the private suite will execute a wide variety of tests, just as a real customer would if they were actually using your code in production. Careful test suite construction is required to check and validate that your program behaves correctly. While the suite has obvious utility for the current deliverable, it will also act as a regression suite as you proceed through the course. Since this is a project, it is expected that the tests from all deliverables continue to pass on your final submission.

### Submitting to AutoTest

You will be able to submit your assignment for validation against the private test suite only once every 12 hours. The private suite will return limited information about the failures it encounters. Since this suite is rate limited, it is highly recommended you extend your project test suite to make your code as robust as possible before testing it against the private suite. There is no downside for submitting your deliverable to the private suite though, so you should make sure you do it at least once.

AutoTest is invoked using a bot on GitHub. If you make a ```@CPSC310bot``` comment on a commit in GitHub the bot will be invoked. Test results will be reported back to the same comment when the test is complete. Some notes to keep in mind:

* For the bot to be invoked, the commit must be on a branch in a configured repository. These will be configured as soon as all repos are set for the course.

* If your code does not cleanly compile (e.g., ```yarn build```), AutoTest will say that the 'tests failed to execute'.

* If a test times out (we use a 30s timeout per-test) it will be 'skipped'. Your pass rate will be calculated as: ```pass / (pass + skip + fail)```. 

We will monitor test suite executions to ensure that our tests are correct; if we encounter a problem we will post to the class forum.

### Submitting Your Deliverable

Your final deliverable will always be the state of the master branch of your repository at the deadline, regardless of when your final submission to the AutoTest suite took place.


---
![] (../readings/figures/CCSA.png "Creative Commons: Attribution-ShareAlike") Reid Holmes