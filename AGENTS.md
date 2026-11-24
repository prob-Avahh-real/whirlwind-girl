# 旋风少女 (Whirlwind Girl)

等距视角解谜游戏，像素级复刻纪念碑谷核心机制。

## 目标平台

| 平台 | 方式 | 交互 | 产出 |
|------|------|------|------|
| 🍎 iOS | Capacitor → Xcode | 触摸 | IPA |
| 🤖 Android | Capacitor → Gradle | 触摸 | APK |
| ⌚ 手表 | 窄屏 + 相机跟随 | 触摸 | 同 APK |
| 👓 智能眼镜 | 窄FOV + SpeechRecognition | 说方向 / 目标 | 同 APK |
| 💍 智能指环 | DeviceOrientation | 倾斜手机=方向 / 甩动=自动寻路 | 同 APK |
| 🦯 智能手杖 | DeviceMotion | 摇晃=方向 / 敲击=确认 | 同 APK |

## 核心机制

- 等距投影 3D 视觉 + 深度排序
- 不可能几何 (Penrose stairs, Escher illusions)
- BFS 路径寻找 + 多模态输入
- 3关渐进式解谜

## Harness / Loop（助手）

- 遵循根 `/Users/skat/AGENTS.md`：**Harness Engineering** + **Loop Engineering**
- Guide = 本文件；Sensor = 下方验证命令；同类失误第二次须沉淀规则或测试（棘轮）
- 开干前写清 **Done**；每切片过验证环；显式停止（成功 / 上限 / 无进展 / 人审）
- 详解：`docs/HARNESS_ENGINEERING.md`、`docs/LOOP_ENGINEERING.md`

## 验证环 / Done

```bash
npm install
npm test          # 若有
npm run build     # 或 build:web
npx cap sync android   # 若有 android/
# 可选：JAVA_HOME=…/openjdk@17 npm run apk:debug
```

**Done 示例**：测试通过（若有）+ web 产物进 `www/`/`dist/` + `cap sync` 无报错。可选穿戴未做可搁置，不纳入强制 Done。
