# 📘 STM32 标准开发流程（CubeMX + VS Code + CMake + Programmer）

适用于：STM32F103（及大多数 STM32 系列）  
目标：建立一套**完整、可复用的嵌入式开发流程**

---

# 📌 一、整体开发链路（核心理解）

```text
CubeMX（配置外设）
        ↓
生成 CMake 工程
        ↓
VS Code（编辑代码）
        ↓
CMake + GCC（编译）
        ↓
STM32CubeProgrammer（烧录）
        ↓
STM32运行程序
```

---

# 🧠 二、各工具职责（必须理解）

|工具|作用|
|---|---|
|STM32CubeMX|配置芯片、生成工程|
|CMake|管理工程结构|
|GCC (arm-none-eabi)|编译代码|
|VS Code|编写代码|
|STM32CubeProgrammer|下载程序|

---

# 🧰 三、完整开发流程

---

# 🔧 第一步：CubeMX 配置工程

## 1️⃣ 创建工程

- 打开 CubeMX
    
- 选择芯片（如 STM32F103C8T6）
    

---

## 2️⃣ 配置外设

根据需求配置：

示例：

- GPIO（LED）
    
- I2C（OLED）
    
- UART（调试）
    

---

## 3️⃣ 配置调试接口

```text
SYS → Debug → Serial Wire
```

---

## 4️⃣ 配置时钟

```text
SYSCLK = 72MHz
```

---

## 5️⃣ 工程生成设置

```text
Project Manager →
Toolchain / IDE → CMake
Compiler → GCC
```

---

## 6️⃣ 生成代码

```text
点击：GENERATE CODE
```

👉 生成内容包括：

- `Core/`（用户代码）
    
- `Drivers/`（HAL库）
    
- `CMakeLists.txt`
    
- `.ioc`（工程配置文件）
    

---

# 💻 第二步：VS Code 开发

---

## 1️⃣ 打开工程

```text
File → Open Folder
选择工程目录（如 f103_led）
```

---

## 2️⃣ 编辑代码

主要编辑：

```text
Core/Src/main.c
Core/Inc/*.h
```

---

## 3️⃣ 添加自定义模块

例如：

```text
Core/Src/oled.c
Core/Inc/oled.h
```

⚠️ 注意：

👉 必须在 CMake 中注册 `.c` 文件

---

## 4️⃣ 修改 CMake（关键）

打开：

```text
cmake/stm32cubemx/CMakeLists.txt
```

在：

```cmake
set(MX_Application_Src
```

中加入：

```cmake
Core/Src/oled.c
```

👉 否则会出现：

```text
undefined reference
```

---

# ⚙️ 第三步：编译工程

---

## 操作流程

```text
Ctrl + Shift + P
→ CMake: Configure

Ctrl + Shift + P
→ CMake: Build
```

---

## 编译成功标志

```text
[100%] Built target xxx
```

---

## 编译输出文件

```text
build/Debug/xxx.elf
```

👉 这是最终烧录文件

---

# 🔌 第四步：烧录程序（Programmer）

---

## 1️⃣ 打开 STM32CubeProgrammer

---

## 2️⃣ 连接开发板

```text
选择 ST-LINK
点击 Connect
```

---

## 3️⃣ 加载程序

```text
选择 .elf 文件
```

路径示例：

```text
build/Debug/f103_led.elf
```

---

## 4️⃣ 下载程序

```text
点击 Download
```

---

## 成功标志

```text
File download complete
```

---

# 🚀 第五步：程序运行

---

## 上电运行方式

- USB供电
    
- 或 ST-Link 供电（部分设备支持）
    

---

## 运行结果验证

例如：

- LED 闪烁
    
- OLED 显示
    
- 串口输出
    

---

# ❗ 六、常见问题总结

---

## 1️⃣ 编译通过但程序异常

原因：

- 逻辑错误
    
- 外设未正确初始化
    

---

## 2️⃣ undefined reference

原因：

- `.c` 文件未加入 CMake
    

---

## 3️⃣ OLED 不亮

原因：

- I2C 地址错误
    
- 接线错误
    
- 模块型号不匹配
    

---

## 4️⃣ 无法连接 ST-Link

原因：

- 驱动问题
    
- 接线错误
    
- 板子未供电
    

---

# 🧭 七、开发最佳实践

---

## ✔ 建议流程

```text
先跑通最小系统（LED）
→ 再加通信（I2C/UART）
→ 再加外设（OLED）
→ 最后做功能
```

---

## ✔ 编码原则

- 不改 CubeMX 自动生成代码
    
- 所有自定义代码写在 USER CODE 区域
    
- 模块化设计（.c + .h）
    

---

# 🎯 八、总结

```text
CubeMX → VS Code → CMake → GCC → Programmer
```

👉 这是一套：

- 工业级开发流程
    
- 可扩展
    
- 脱离 IDE（Keil）
    

---

# 👨‍🏫 给初学者建议

👉 不要一开始写复杂功能  
👉 先打通整个开发链路

---

# 🚀 九、进阶方向

- FreeRTOS
    
- SPI / ADC / DMA
    
- GUI界面（OLED UI）
    
- 物联网通信
    

---