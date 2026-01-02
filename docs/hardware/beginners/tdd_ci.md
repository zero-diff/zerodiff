# TDD/CI

### Continuous Integration

Use TeamCity. The end. (Seriously.)

### TeamCity on AWS

The cool thing about TeamCity is that it can do high-quality CI for just about everything there ever was: desktop app, native mobile, webapp, backend, firmware and yes, automated monkey tests for hardware. Even if you already use an outsource CI solution for the backend or web, you'll be much more effective if you adopt a tool like TC that can literally build just about any weird thing that's scriptable on Linux, Windows or Mac instances. Spinning up an instance of TC on AWS is nearly plug-and-play. This also allows you to set it up to spin up buiild workers as needed to deal with load.

[https://confluence.jetbrains.com/display/TCD9/Setting+Up+TeamCity+for+Amazon+EC2](https://confluence.jetbrains.com/display/TCD9/Setting+Up+TeamCity+for+Amazon+EC2)

### TDD

It's hard to know what firmware, RTOS, builder platform, etc. that anyone will use for their hardware target. Our experience is largely with C/C++ and support for unit testing with CUnit is pretty good. Combined that with an IDE that supports CUnit (all the Eclipse variants) and you can have your firmware developers follow the red-green-refactor TDD process. 

### End-to-end Testing

There's really not much point to E2E testing unless you do it on live hardware. Likely your build chain and deploy process is pretty messy and not automated to hardware. *THIS IS OK.* Your job as a beginner is to focus on user value. Just make good recipe documents for your build-deploy-test cycle. Maintain them via Kaizen like all of your processes! If your product is hit, you can always turn those good process recipes into automated monkey tests later.

### Wait, Did You Say, "No automated toolchain-deploy to hardware jig tests?!"

Yes! Invest nearly all of your time in design, user testing and ethnographic/market study. Don't invest a lot in automation (yet). If your product is so desirable that users complain about the occasional regression, then you're in good shape! If your product is perfection-on-a-stick, but undesirable, then you're sunk. (That's a clear sign you're still pre-PMF.) The first case is likely easily fixed, and it doesn't matter if you burn through a few users - the evidence says there will be tons more. In the second case, that's not easy to fix! Maybe it's even impossible to fix.