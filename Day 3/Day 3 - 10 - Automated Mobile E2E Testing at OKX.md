Talks about having a Device Farm to do Integration Testing in OKX, using Appium

**The Test Pyramid**
--- More Expensive, Slower ---
E2E
Integration Test
Unit Test
--- Cheaper, Faster ---
To save cost of QA team and reduce the burden of developer self testing, spend time on automated test

**Test Framework**
- Appium
- Why Appium?
	- Its open source and cross-platform, just need to maintain a single set of test case, can build for both ios and android
	- Cost of maintaining test cases gets lower
	- Client-Server Architecture -> plan to setup test server internally (sort of a device farm)
- For iOS, using XCUITestFramework on Appium
- Appium Client -> Server -> Send Test to Devices

**Architecture**
- Version 0
	- Test Script -> Appium Server -> Devices

- Jenkins -> Pull Code -> Tell Sonic to establish connection to Device
- Jenkins send config to establish the connection to devices
- Initialize Driver objects so that Client can talk to devices
