<p align="center">🎉Matrix UI自动化Driver核心</p>
<p align="center">
  <a href="https://github.com/felixyang007/matrix-driver-core/blob/main/README.md">
    English
  </a>
  <span>| 简体中文</span>
</p>

## matrix-driver-core是什么？

matrix-driver-core可以脱离Appium，直接与WebDriverAgent或UIautomator2交互，减少了Appium的通信层，让测试更快更稳定。

## 在你的Java代码中使用

### 引用库
#### Maven
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

### 代码

```java
package org.cloud.sonic.driver.ios;

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

        //更多...
    }
}
```

## 开源许可协议

[License](LICENSE)
