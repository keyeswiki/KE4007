# Arduino

### 1. Arduino编程软件介绍

**Arduino**是一种开放源代码电子原型平台，结合了可编程的微控制器和易于使用的硬件与软件。Arduino IDE提供了一个简洁的环境，使开发者能够轻松编写代码并上传到Arduino板上，广泛应用于教育、创客项目及物联网设备的开发上。

Arduino使用一种基于C/C++的语言，适合初学者和专业人士，能够迅速实现从简单到复杂的电子控制与传感器应用。

---

### 2. 连接图

**![KE4007](media/a482b43937d422b1e2bdbeb36aa1f798.png)**

### 3. 测试代码

```cpp
int redPin = 6;   // R 红色LED 控制引脚 连接到Arduino的 6脚
int greenPin = 5; // G 绿色LED 控制引脚 连接到Arduino的 5脚
int bluePin = 3;  // B 蓝色LED 控制引脚 连接到Arduino的 3脚

void setup() {
    pinMode(redPin, OUTPUT);   // 设置redPin对应的管脚6为输出
    pinMode(greenPin, OUTPUT); // 设置greenPin对应的管脚5为输出
    pinMode(bluePin, OUTPUT);  // 设置bluePin对应的管脚3为输出
}

void loop() { // run over and over again
    // Basic colors:
    color(0, 255, 255); // 红色亮
    delay(1000); // 延时一秒
    color(255, 0, 255); // 绿色亮
    delay(1000); // 延时一秒
    color(255, 255, 0); // 蓝色亮
    delay(1000); // 延时一秒

    // Example blended colors:
    color(0, 0, 255);   // 黄色亮
    delay(1000); // 延时一秒
    color(127, 255, 0); // 紫色亮
    delay(1000); // 延时一秒
    color(0, 0, 0);     // 白色亮
    delay(1000); // 延时一秒
    color(255, 255, 255);// 关闭led
    delay(1000); // 延时一秒
}

void color(unsigned char red, unsigned char green, unsigned char blue) { // 颜色控制函数
    analogWrite(redPin, red);
    analogWrite(greenPin, green);
    analogWrite(bluePin, blue);
}
```

### 4. 测试结果

按照上图接好线，烧录好代码，上电后，RGB模块会陆续显示红色1秒，绿色1秒，蓝色1秒，黄色1秒，紫色1秒，白色1秒，停止显示1秒，然后循环交替。

