<p align="center">🎉The Matrix UIAutomation Driver Core</p>
<p align="center">
  <span>English |</span>
  <a href="https://github.com/felixyang007/matrix-driver-core/blob/main/README_CN.md">
     简体中文
  </a>
</p>

## What is matrix-driver-core?

matrix-driver-core can be separated from appium and interact directly with webdriveragent or uiautomator2, which reduces the communication layer of appium and makes the test faster and more stable.

## Use in Java code

### Add dependency
#### Maven Central

```xml

<dependency>
    <groupId>io.github.soniccloudorg</groupId>
    <artifactId>sonic-driver-core</artifactId>
    <version>1.1.30</version>
</dependency>
```

#### Gradle

```
implementation 'io.github.soniccloudorg:sonic-driver-core:1.1.30'
```

### Code

```java
package org.cloud.sonic.driver.ios;

import org.cloud.sonic.driver.ios.enums.IOSSelector;
import org.cloud.sonic.driver.common.tool.SonicRespException;

public class MyTest {

    public void test() throws SonicRespException {
        IOSDriver iosDriver = new IOSDriver("http://localhost:8100");
        iosDriver.showLog();

        //touch
        iosDriver.swipe(100, 256, 50, 256);
        iosDriver.tap(150, 81);
        iosDriver.longPress(150, 281, 1500);
        iosDriver.performTouchAction(new TouchActions().press(50, 256).wait(50).move(100, 256).wait(10).release());

        //element
        iosDriver.findElement(IOSSelector.XPATH, "//XCUIElementTypeTextField").click();

        //more...
    }
}
```

## LICENSE

[License](LICENSE)
