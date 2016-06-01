## Automated Monkey Testing (AMT)

A continuous and complete simulation of user interactions against a design. You run automated monkey tests against each commit using the continuous integration (CI) system. 

The alternative, perhaps most common way to accomplish this kind of testing, is human-scripted testing. 

**Don't do that!** 

Human-driven, scripted testing is mindless and *boooring*, and the more someone runs them, the more numb they become. This is a recipe for tests that hardly ever get run, and when they do get run, the effort is generally perfunctory and sloppy.

### Even your first design iteration should be testable

> When you engage in **any** design, you must start with the question: "what's testable about this design?"

The right way to test is automation: continuous integration, unit and end-to-end tests. You'll never get to automated testing unless the tests are part of the design process. A side benefit of doing this in the design process is that when you send a revision to mass production, your vendor partners have a way to validate their work as part of the QA/acceptance testing. (You, really, really, really don't want to race around trying to create some kind of manufacturing acceptance test just before manufacture because it will force you to redesign the PCB and that will take almost as much work as the original development!)

###Test criteria fall into four broad categories:

####Usability

The whole reason to follow the ZeroDiff process is to rapidly iterate on your design assumptions. The design stories that flow out of the sprints should represent the base criteria that validates if the design meets user need. As soon as a prototype emerges from the shop, the test team needs to validate the prototype against these stories.

####Survivability

One problem with the "works-like/looks-like" development model is there is no way to know how difficult it will be to design a production version that can survive contact with users. Breaking the production process into two phases like this will take more total development hours, and it creates a lot of uncertainty about how long it will actually take to get to market.

####Manufacturability

Each time the prototype team produces a design iteration, they should perform a design-for-manufacture (DMF) review. Each iteration is a chance for the production team to inform the design team of ways to improve costs, simplicity, reliability and quality. One nice thing about the ZeroDiff process is that small changes like this are easy to digest, so the two teams can make a lot of progress without conflict.

####Reliability

Probably the most unnerving part of hardware development are transient field failures. E.g. glitches, reboots, freezes, bricking or random weirdness in the user experience. The best way to defend against transient failures is to force the combined firmware and hardware through automated testing for every commit.

## Steps to get to AMT

### Burn-in/Manufacture Jigs

Probably the easiest way to start down the road to AMT is to start with a test/flash jig for any new design. Resist the temptation to simply place a JTAG/SWD header on the PCB that fits your programming pod. It will be difficult for an outside vendor partner to reach any meaningful scale if they require access to a programming pod on the manufacturing floor. Even if you don't have the ability to fabricate a jig now, the presence of the flash/debug bus as test points means you can more easily automate this for production later without having to redesign the board. Whether the device ever reaches scaled production or not, it costs almost nothing to add this capability in the beginning.

### Test Harness and Test Points

Closely related to burn-in jigs are test points. Any I/O, button, switch, sensor or communication bus should have a corresponding test point (pad) accessible somewhere on the PCB. These should all be on the same side, probably on what would be the "bottom" if the device has a strong user-facing side. The test harness can use pogo-pins to reach these test points. Even if you don't have the capability to fabricate a test harness/jig, adding these test points now allows you easily incorporate a test harness later without having to redesign the board.

Eventually you want these test points to drive automated tests that simulate user behaviors to test on-board subsystems like communications or sensor readings. The same automated, scripted tests you use in AMT work for manufacturing validation and QA. The assembly line worker should be able to push the completed device into a harness and press a button that flashes the device and runs a validation battery that results in a go/no-go indication for the assembly worker.

### Scripted Development Environment

Almost all firmware development toolchains now support scripted development. Embrace this early and integrate it into a continuous integration tool like TeamCity. This is not hard to do, and the benefits are enormous. Once the scripted testing is in place, your development team has a convenient place to hang firmware unit tests. Scripted testing is also a good place to hang automated monkey tests. Once you have even one of these automated tests, it's much easier for the team to add subsequent tests.

### Report Bugs as Unit Tests

A good QA and development team is able to express bugs as unit or E2E tests that fail. Having a place to add these tests to automated testing means that you can get coverage against regressions or closely related failures.