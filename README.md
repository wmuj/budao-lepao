<div align="center">

# 🏃‍♂️ 步道乐跑校园定向跑全自动闭环智能体
### `budao-lepao` · Autonomous Closed-Loop Campus Running Agent

[![Python](https://img.shields.io/badge/Python-3.10%20%7C%203.11%20%7C%203.12-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![OCR](https://img.shields.io/badge/Vision%20Engine-RapidOCR%20(ONNX)-FF6F00?style=for-the-badge&logo=onnx&logoColor=white)](https://github.com/RapidAI/RapidOCR)
[![Emulator](https://img.shields.io/badge/Emulator-MuMu%20Player%2012-00B4D8?style=for-the-badge)](https://mumu.163.com/)
[![Community](https://img.shields.io/badge/Community-LINUX%20DO-24292e?style=for-the-badge&logo=linux&logoColor=white)](https://linux.do)
[![GitHub stars](https://img.shields.io/github/stars/wmuj/budao-lepao?style=for-the-badge&color=gold)](https://github.com/wmuj/budao-lepao/stargazers)

<br/>

**⚡️ 告别黑产抓包逆向 · 基于计算机视觉闭环与空间数值梯度的物理级全自主校园跑步机器人 ⚡️**

[💡 项目初衷](#-项目初衷) •
[📸 运行效果](#-实机运行效果) •
[🧠 核心算法原理](#-核心算法与技术创新) •
[🏗️ 系统架构](#-系统工程架构) •
[🚀 快速上手](#-快速上手) •
[❓ 常见问题](#-常见问题-faq) •
[⚖️ 免责声明](#-免责声明-disclaimer)

</div>

---

## 💡 项目初衷

> **"早晨 6:30 的闹钟响了，但我只想在晚上酣畅淋漓地夜跑。"**

许多高校对大学生实施了强制性的**清晨晨跑打卡制度**（通常限定在清晨 06:30 ~ 07:30 时段），一旦缺卡将直接影响学期体育成绩甚至奖学金评定。然而，当代大学生的作息规律、课业安排各不相同，大量同学**更倾向于在下午或晚间课余时间自主锻炼**，却常常受困于严苛死板的清晨打卡规则。

本项目专门**为了解决“早起实在起不来、但课余愿意自主跑步”的同学们的晨跑痛点**而研发。  
我们**不采用任何修改内存、Hook、逆向封包或破解加密算法的高危黑产手段**，而是基于 Android 虚拟化底座、计算机视觉 OCR 状态识别与自适应空间数值梯度算法，在宿主机侧构建了一套完全仿真人类真实操作与运动规律的合规闭环系统。

---

## 📸 实机运行效果

<div align="center">
  <table style="margin: 0 auto; border-collapse: collapse; text-align: center;">
    <thead>
      <tr style="background-color: #f6f8fa;">
        <th align="center" width="33%"><b>📍 跑步中实时监控与智能打卡</b></th>
        <th align="center" width="33%"><b>⏱️ 闭环配速控制与指标结算</b></th>
        <th align="center" width="33%"><b>🗺️ 最终达标轨迹与状态</b></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td align="center"><img src="assets/running_progress.png" width="280" alt="跑步中状态"/></td>
        <td align="center"><img src="assets/run_result_metrics.png" width="280" alt="配速结算指标"/></td>
        <td align="center"><img src="assets/run_track_map.png" width="280" alt="完成轨迹"/></td>
      </tr>
      <tr>
        <td align="center"><sub>实时 RapidOCR 异步获取打卡点距离<br/>自适应正交负梯度自动逼近</sub></td>
        <td align="center"><sub>严格锁死 <code>5'59" ~ 6'00"/km</code> 黄金配速<br/>步频动态注入，完全消除异常波动</sub></td>
        <td align="center"><sub>打卡点数达标 (2/2) + 里程达标 (2.05km)<br/>自动长按滑动结算，成绩即时入库</sub></td>
      </tr>
    </tbody>
  </table>
</div>

---

## 🥊 方案对比：为什么这是终极解决方案？

| 维度 | 传统抓包 / 逆向协议挂 (已淘汰) | 传统 UI 脚本 / 模拟器死循环 (极不稳定) | 🌟 本项目 (`budao-lepao`) |
| :--- | :--- | :--- | :--- |
| **底层机理** | 逆向 API、伪造加密签名 (SM4/AES/HMAC) | 裸 `adb shell input` + `uiautomator dump` | **视觉 OCR 离线闭环 + 空间数值梯度寻优** |
| **风控安全性** | ❌ **极度危险**。服务端接口随时迭代风控 | ⚠️ **高危**。无动态步频，轨迹生硬易被判作弊 | 🛡️ **极高**。物理传感器摇一摇脉冲 + 真机级自然航向 |
| **打卡点适应性**| ⚠️ 依赖打卡点数据库；未录入则彻底失效 | ❌ **无法应对随机点**，只能跑固定路线 | 🎯 **全自适应**。无需提前预录坐标，梯度实时逼近 |
| **系统稳定性** | ❌ 证书绑定与网络环境变化即瘫痪 | ❌ 跑步页计时器刷新引发 dump `rc=137` 崩溃 | ⚡️ **毫秒级高可用**。独立异步线程 OCR，零崩溃 |
| **配速达标率** | ⚠️ 固定算法，打卡停留易导致均速超标 | ❌ 无动态调速能力，极易超出合格区间 | 🎯 **100% 达标**。闭环控速锁死 6'00"，超时自动补齐 |

---

## 🧠 核心算法与技术创新

### 1. 2D 正交数值梯度动态寻路算法 (Orthogonal Gradient Descent)
步道乐跑的核心机制是**“每跑满一定距离后由服务端动态分配下一个随机打卡点”**，App 界面仅显示目标点名称及模糊的“距你 $d$ 米”，不暴露经纬度。

本项目通过在二维地理平面进行微步正交探测（Orthogonal Probing）：
$$\frac{\partial d}{\partial x} \approx \frac{d(x + \Delta x, y) - d(x, y)}{\Delta x}, \quad \frac{\partial d}{\partial y} \approx \frac{d(x, y + \Delta y) - d(x, y)}{\Delta y}$$

构造空间距离梯度向量：
$$\nabla d(x, y) = \begin{pmatrix} \frac{\partial d}{\partial x} \\ \frac{\partial d}{\partial y} \end{pmatrix}$$

运动控制引擎直接沿**负梯度方向**推进：
$$\vec{v} = - v_{\text{run}} \cdot \frac{\nabla d}{\|\nabla d\|_2}$$

当距离衰减至目标点阈值（$\le 20\text{m}$）时，系统自动切入原地微动巡航状态，等待 App 触发打卡成功提示后，无缝切入下一个随机打卡点。

### 2. RapidOCR 离线视觉异步状态机
* **痛点突破**：跑步中界面的计时器每秒刷新，Android 原生 `uiautomator dump` 会因等待 Accessibility 空闲而超时被系统 SIGKILL（`rc=137`）。
* **解决方案**：绕过 UIAutomator，采用 `adb exec-out screencap -p` 直接读取帧缓冲区（Framebuffer），交由本地轻量化 **ONNXRuntime + RapidOCR** 推理引擎，在 150ms 内完成局部仪表盘（里程、用时、打卡点）高精文本抽取，为控制循环提供稳定的感知反馈。

### 3. 动态时间补偿与配速闭环控制器
为保证最终平均配速严格落在高校要求的合格区间（$3'00" \sim 8'00"/\text{km}$，黄金均速 $6'00"/\text{km}$）：
* **停留补偿机制**：每次在打卡点停留等待打卡会损失约 10~15 秒时间；
* **闭环动态调速**：
  $$v_{\text{target}}(t) = \text{clamp}\left(\frac{D_{\text{total}} - D(t)}{T_{\text{target}} - T(t)}, \, 2.30\text{ m/s}, \, 4.40\text{ m/s}\right)$$
  打卡完成后系统自动平滑加速追回损失时间，里程达标时配速完美收敛于 $6'00"/\text{km}$。

### 4. 真实物理加速度计脉冲注入
* App 内部通过传感器事件监听（SensorEventListener）检测加速度峰谷判定步数与防作弊运动状态；
* 系统通过 MuMu 内核网关以符合真实步频（175~185 spm）的频率定时发送 `shake` 脉冲，使虚拟传感器产生 $9.8 \to 40 \to 30 \to 9.8\text{ m/s}^2$ 的生理级峰谷，确保步数、步频与里程在高校后台完全拟合。

---

## 🏗️ 系统工程架构

```text
┌────────────────────────────────────────────────────────────────────────┐
│                        CampusRunner 主决策中枢                          │
└───────┬────────────────────────────────────────────────────────┬───────┘
        │ 状态轮询 (0.5s)                                        │ 坐标/传感器控制 (1.0s)
        ▼                                                        ▼
┌───────────────────────────────┐        ┌───────────────────────────────┐
│     StateWatcher 观测线程      │        │     MuMuLocationClient 底座   │
├───────────────────────────────┤        ├───────────────────────────────┤
│ • exec-out screencap 截图     │        │ • WGS-84 / GCJ-02 / BD-09 矩阵 │
│ • RapidOCR (ONNX) 局部文字识别 │        │ • HTTP 网关虚拟定位下发        │
│ • RunState 状态标准化解析     │        │ • StepFeeder 真实步频模拟      │
└───────────────────────────────┘        └───────────────────────────────┘
        │                                                        │
        └───────────────────────┬────────────────────────────────┘
                                ▼
        ┌────────────────────────────────────────────────┐
        │      网易 MuMu 模拟器 (Android 12 / 1080x1920) │
        │      步道乐跑 官方客户端 (无注入 / 无篡改)      │
        └────────────────────────────────────────────────┘
```

---

## 📂 仓库目录规范

```
budao-lepao/
├── README.md                 # 本项目完整技术文档与免责声明
├── LICENSE                   # MIT 开源许可证
├── requirements.txt          # Python 依赖清单
├── .gitignore                # 严密防泄露配置 (隔离全部个人凭据与大文件)
├── campus_run.py             # 核心生产主控：正交梯度寻优 + 配速闭环 + 异常容错
├── screen_state.py           # 机器视觉模块：RapidOCR 离线局部截屏解析器
├── campus_state.py           # 状态模型：RunState 实体类与数据解析
├── campus_run_sim.py         # 仿真平台：内置虚拟时钟的极速离线仿真器
├── start_campus_run.bat      # Windows 一键执行入口
├── run_afternoon_once.bat    # 定时调度/自动化任务执行脚本
├── start_assistant.py        # 辅助调试启动工具
├── assets/                   # 项目说明配图 (完全脱敏)
│   ├── running_progress.png  # 寻路中截屏
│   ├── run_result_metrics.png# 配速结算图
│   └── run_track_map.png     # 轨迹成果图
├── lepao/                    # 底层虚拟化通信与传感器驱动引擎
│   ├── __init__.py
│   ├── geo.py                # 大地测量学坐标转换 (WGS-84/GCJ-02/BD-09) 与测距
│   ├── mumu.py               # MuMu 本地网关通信、ADB 指令与窗口状态管理
│   ├── sensors.py            # 加速度计脉冲发生器与步频自适应调节
│   ├── routes.py             # 操场跑道环线拟合模型
│   ├── track.py              # 运动轨迹建模与序列化
│   └── autolink.py           # 路径连通性检测
└── tools/                    # 历史单点测试与调试工具集
    ├── punch_gate.py         # 目标点定点测试
    ├── punch_cp2.py          # 打卡点直通测试
    ├── run_trigger_cp2.py    # 触发距离步进测试
    ├── run_to_checkpoint.py  # 寻路回归测试
    ├── run_300m_test.py      # 短程闭环测试
    └── run_freerun_2km.py    # 操场自由跑测试
```

---

## 🚀 快速上手

### 1. 环境准备
1. **操作系统**：Windows 10 / 11 64位
2. **Python 环境**：Python 3.10 ~ 3.12
3. **Android 模拟器与 App 版本（防闪退关键！）**：安装 [网易 MuMu 模拟器 12](https://mumu.163.com/)
   * **必须满足双条件①（系统版本）**：新版 MuMu 官网包默认创建的可能是 **Android 15** 实例，请务必在 **「MuMu 多开器」** 中明确新建并选用 **Android 12** 实例，并在设置中**关闭 ROOT 权限**
   * **必须满足双条件②（App 版本）**：请安装官方历史版本 **步道乐跑 `v4.3.1`（`versionCode 231`）**！
     * ❌ **不要安装最新官方 `v4.3.3`**：4.3.3 新增了 `libkadp.so` 加固壳与 `KwProtectSDK` 模拟器检测自杀逻辑，**即使在 Android 12 + DirectX + 关闭 ROOT 下也会直接闪退**；
     * ❌ **不要使用 `v4.2.6` 及更早版本**：服务端现已提示强制更新，无法进入首页；
     * > 本仓库遵循开源规范，**不分发任何官方或第三方修改版 APK**，请自行通过正规历史版本渠道核对官方签名后获取 `v4.3.1`。
   * 模拟器分辨率建议配置为手机竖屏：`1080 x 1920` (DPI 480)，设备型号选择常见真机型号（如 Samsung SM-S9080 等）
   * 模拟器系统设置中开启定位服务（高精度模式），**不要开启任何第三方模拟定位（Mock Location）应用**
   * 安装完成后，建议先执行一次环境与设备特征自检：
     ```bash
     python campus_run.py --check
     ```

### 2. 安装项目依赖
克隆本项目到本地后，在命令行执行：
```bash
git clone https://github.com/wmuj/budao-lepao.git
cd budao-lepao
pip install -r requirements.txt
```

### 3. 一键运行正式跑步
确保 MuMu 模拟器已开启并在前台/后台运行，步道乐跑处于首页，在项目根目录下双击运行：
```bat
start_campus_run.bat
```
或通过命令行自主调优控制参数：
```bash
python campus_run.py --pace 6.0 --km 2.05 --cps 2 --auto-start --auto-finish
```

#### CLI 参数完整说明：
| 参数 | 类型 | 默认值 | 参数含义与作用 |
| :--- | :---: | :---: | :--- |
| `--pace` | `float` | `6.0` | 目标平均配速（单位：分/公里）。`6.0` 即 `6'00"/km`，系统将动态控速锁定该值 |
| `--km` | `float` | `2.05` | 目标总跑步里程（单位：公里）。建议略大于高校要求的 2.00 km 防止浮点误差 |
| `--cps` | `int` | `2` | 需打卡的随机点数。跑满打卡点并达到里程后系统才允许收尾 |
| `--auto-start` | `flag` | 开启 | 启动时自动点击 App 首页的“开始乐跑”，并全自动识别跳过各类权限提示弹窗 |
| `--auto-finish` | `flag` | 开启 | 达标后自动长按结束按钮并确认保存，全程无需人工值守 |
| `--vm-index` | `int` | `0` | 指定 MuMu 多开实例编号（也可通过环境变量 `MUMU_VM_INDEX` 配置）。新建 Android 12 多开实例时通常为 `1` |
| `--start-lat` / `--start-lon` | `float` | 示例坐标 | 起始点 WGS-84 纬/经度（也可通过 `LEPAO_START_LAT` / `LEPAO_START_LON` 环境变量指定） |
| `--check` | `flag` | 关闭 | 仅执行启动前环境与设备特征自检（Android 版本、App 版本、ROOT、Mock 定位、传感器、设备指纹），不启动跑步 |
| `--skip-check` | `flag` | 关闭 | 跳过启动前自检直接运行 |

### 4. 极速离线仿真（无须模拟器）
本项目内置了完备的离线闭环仿真测试套件，使用虚拟时钟和假 App 接口验证算法：
```bash
python campus_run_sim.py
```
*可在 0.5 秒内极速推演 2.05km 跑步全过程，验证正交梯度下降寻路及起跑延时追赶逻辑的数学正确性。*

---

## 🛠️ 全自动无人值守（定时任务集成）

配合操作系统的“任务计划程序”（Windows Task Scheduler）或第三方定时工具，可以在每天清晨指定时段（如 06:35）静默唤醒执行：
1. 自动调用 `MuMuManager.exe` 唤醒并拉起模拟器系统；
2. 自动建立 ADB 本地通道并激活 GPS 定位模式；
3. 自动进入步道乐跑、自动起跑、双打卡点寻路打卡、配速闭环调控、自动结算退出；
4. 运行结果可重定向至日志文件（`morning_run_latest.log`），全流程零弹窗干扰。

---

## ❓ 常见问题 (FAQ)

### Q1：为什么我切了 MuMu Android 12 + DirectX + 关闭 ROOT，安装官方步道乐跑还是闪退？

这是目前最常见的踩坑点——**光切到 Android 12 还不够，还必须避开 `v4.3.3` 官方新包！**

| 步道乐跑官方版本 | MuMu Android 12（关 ROOT） | MuMu Android 15 | 原因说明 |
| :--- | :---: | :---: | :--- |
| **`v4.2.6` 及更早** | ❌ 强制更新 | ❌ 强制更新 | 服务端已停用旧版，打开即弹窗要求升级 |
| **`v4.3.1`（`versionCode 231`）** | ✅ **实测稳定可用** | ⚠️ 易触发风控异常 | **当前推荐版本**（2026-11 持续实测正常打卡结算） |
| **`v4.3.3`（`versionCode 233`，最新）** | ❌ **启动即闪退** | ❌ **启动即闪退** | 新增 `libkadp.so` 壳 + `KwProtectSDK` 模拟器检测自杀（`UniverseSecNo2 -> SIGKILL`）；Android 15 还叠加 ART ABI 崩溃（`SIGSEGV`） |

**推荐解决步骤（官方原版，无需脱壳改包）：**
1. 在 **MuMu 多开器** 中新建/使用 **Android 12** 实例，并在设置中**关闭 ROOT 权限**（若显卡渲染异常再尝试切 DirectX）；
2. 卸载模拟器内已安装的 `4.3.3` 版本，自行从正规历史版本渠道获取并安装官方签名的 **`v4.3.1`（`versionCode 231`）**（本仓库不分发 APK）；
3. 先运行启动前自检确认版本、传感器和设备特征均通过：
   ```bash
   python campus_run.py --check --vm-index 0
   ```
   （如果新建的 Android 12 实例编号为 `1`，请将 `--vm-index` 改为 `1`）。

> **关于第三方脱壳/重打包 `4.3.3` APK**：社区中存在剥离 `libkadp.so` / `KwProtectSDK` 的重打包方案，但该类改包使用非官方 debug 签名，QQ/微信登录受限且可能引入额外风控风险。本项目坚持**官方原版、零注入/零篡改**原则，不分发也不推荐使用修改版 APK，优先使用 **MuMu Android 12 + 官方 `v4.3.1`** 即可稳定运行。

### Q2：为什么跑了几分钟弹出“系统检测到您当前跑步行为异常，已结束跑步”？

结合实测与客户端检测机制，触发该提示主要有以下 3 个原因：
1. **仅推送虚拟定位，未同步注入加速度计步频脉冲**：MuMu 静止时加速度计恒为 `9.81 m/s²`，客户端 `TYPE_ACCELEROMETER` 计步为 0 且运动状态 MAD 判定为静止，会直接触发 `cheatMonitoringPlan` 异常判定。请通过 `campus_run.py` 完整闭环运行，确保后台 `StepFeeder` 摇一摇脉冲正常工作；
2. **使用了 `addTestProvider` / 系统 Mock Location**：通过测试定位接口下发的坐标会携带 `mock`（`isFromMockProvider=true`）标志，即使速度字段正常也会在 2~3 分钟内被判定异常。请关闭所有第三方模拟定位，仅使用 MuMu 原生网关定位；
3. **Android 15 环境 / ROOT / 设备指纹异常**：建议统一使用 **MuMu Android 12 + 官方 `v4.3.1` + 关闭 ROOT**，并在 MuMu 设备设置中选择常见真机型号（如 Samsung SM-S9080 等）与随机 IMEI。运行 `python campus_run.py --check` 即可在起跑前一键排查上述全部项。

---

## 🤝 鸣谢与社区认可

本项目由 **[LINUX DO 社区](https://linux.do/)** 提供交流与开源推广支持，认可并践行「真诚、友善、团结、专业」的开源极客精神！

---

## ⚖️ 免责声明 (Disclaimer)

1. **教育与科研目的**：本项目代码及技术文档仅供个人学习 Python 自动化控制、图像处理与计算机视觉（OCR）、空间几何算法及 Android 移动端自动化测试研究之用。
2. **严禁违规与作弊**：严禁将本项目用于任何学校体育考试作弊、商业代跑或任何侵犯步道乐跑平台服务协议的非正当用途。因不当使用该项目产生的任何纠纷、账号异常或校纪违规处罚，均由使用者本人全权承担，开发者概不负责。
3. **健康倡议**：体育运动的本质是强健体魄与培养坚韧意志。建议同学们在清晨或课余时间走出宿舍、多参与真实健康的户外体育锻炼。
4. **版权与调整**：本项目中涉及的所有第三方商标、Logo 与应用名称（如步道乐跑、MuMu 模拟器等）版权均归各自所有者所有。如相关方认为存在不当内容，请提交 Issue 或联系开发者进行调整。

---

<div align="center">
  <b>如果本项目对你的自动化与算法学习有所启发，欢迎点一个 ⭐ Star 支持一下！</b>
</div>
