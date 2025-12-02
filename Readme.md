# 3DOF-Robotic-Arm-Control

基于张大头步进电机的RRR构型三自由度机械臂实现 控制部分

基于我的项目 [LanternCX/ZDT-PTZ: 基于张大头步进电机的二维云台实现与串口协议二次封装](https://github.com/LanternCX/ZDT-PTZ) 开发

## 快速开始

1. **环境准备**

   ESP32 + VSCode + PlatformIO

2. **克隆仓库**

   ```
   git clone https://github.com/LanternCX/ZhiGrip-Control.git
   cd ZhiGrip-Control
   ```

在 `PIO` 中打开仓库并烧入代码就可以通过[串口命令](#串口命令)进行调试

## 串口命令

在 `Main.cpp` 中定义了一些串口命令，可以当作是示例代码

| 命令前缀 | 参数格式              | 描述                                               | 示例             |
| -------- | --------------------- | -------------------------------------------------- | ---------------- |
| `SPEED`  | `a1 a2 a3 <a4>`       | 第一第二第三关节转速以及夹爪转速（也可以三个参数） | `SPEED 0 0 0 50` |
| `ANGLE`  | `a1 a2 a3` (整数角度) | 第一第二第三关节角度                               | `ANGLE 90 30 0`  |
| `CATCH`  | `ON OFF` (整数角度)   | 在当前角度基础上增加水平 (x°) 与垂直 (y°)          | `CATCH ON`   |

**注意事项**：

- 字符串以 `\r\n` 结尾都可以
- 参数范围会在代码中通过 `max/min` 限制。
