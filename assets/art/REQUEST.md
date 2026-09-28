# 美术素材需求（萌宠小牧场）

《萌宠小牧场》是一款日系萌系宠物经营养成网页游戏，纯前端单文件 `index.html`，所有美术走 SVG。
下面是还缺的素材清单，按批次排了优先级。**按批次的顺序做，做完一批提交一批就行。**

## 通用技术规格（每张图都必须遵守）

- 格式：纯 SVG 文件，透明背景，**不要** `<image>` 外链、不要外部字体、不要 `<script>`
- **不要** `<filter>` / `<feGaussianBlur>`（游戏每帧绘制几十只动物，滤镜会掉帧）
- **不要**内嵌 CSS 动画（`<animate>` / `@keyframes`）：呼吸、眨眼、摇尾巴都由游戏代码负责
- 描边：圆头圆角 `stroke-linecap="round" stroke-linejoin="round"`，描边色 `#7A5B48`，线宽 3（120 画布基准）
- 画风：Q 版三头身，头大身小，正面朝观众，线条圆润柔和，腮红 `#FFA8B8` 半透明
- 请用 `<g>` 分层命名（body / head / ear / eye / cheek / tail 等），方便后续做局部动画

## 批次 A —— 动物全身贴图（10 张代表品种已完成 ✅）

这 10 张已经画好了，**请照着它们的画风做其余 42 个品种**（描边 `#7A5B48` 3px 圆头圆角、Q 版三头身、腮红 `#FFA8B8`）。
打开 `assets/art/preview.html` 可以一次看全部素材。

路径：`assets/art/pet/<物种>.<品种id>.svg`，例如 `assets/art/pet/dog.shiba.svg`

画布 `viewBox="0 0 120 120"`，主体居中，**脚底贴齐 y=112**，左右留 6px 余量。
再出一张同款 `assets/art/pet/<物种>.<品种id>.face.svg`（只画头部特写，viewBox 0 0 64 64），用于头像/图鉴。

| 文件名 | 中文名 | 主色 | 肚皮/浅色 | 细节色（耳/鼻） | 特征备注 |
|---|---|---|---|---|---|
| `pet/dog.shiba.svg` | 柴犬 | `#E8A33D` | `#FFF4E2` | `#F6C79B` | 耳型:tri |
| `pet/cat.orange.svg` | 橘猫 | `#F2A65A` | `#FFF0DC` | `#F8C99B` | 花纹:stripe/#E08C3C，耳型:tri |
| `pet/hamster.golden.svg` | 金丝熊 | `#F3C98B` | `#FFF3DF` | `#F8D9AC` | 耳型:round |
| `pet/guineapig.shorthair.svg` | 短顺 | `#E8C08A` | `#F7E4C6` | `#F3CFA6` | 耳型:round |
| `pet/capybara.normal.svg` | 水豚 | `#A98156` | `#C29A6B` | `#8E6B45` | 耳型:tiny |
| `pet/duck.yellow.svg` | 小黄鸭 | `#FFE066` | `#FFF3C4` | `#FFE066` | 头色:#FFE066 |
| `pet/pony.cream.svg` | 奶油马 | `#F6E3C5` | `#FFF8EC` | `#F6E3C5` | 鬃毛:#E8CBA0，耳型:tri |
| `pet/squirrel.red.svg` | 红松鼠 | `#C96A3B` | `#E9A87F` | `#F0C0A2` | 耳型:tuft |
| `pet/alpaca.cream.svg` | 奶白羊驼 | `#F5EBDD` | `#FFFBF4` | `#E4D6C2` | 耳型:spike |
| `pet/pig.pink.svg` | 粉小猪 | `#F7B8C4` | `#FFD9E1` | `#F5A0B0` | 耳型:tri |

## 批次 B —— 补齐其余 42 个品种

同 A 的规格，文件名沿用 `<物种>.<品种id>.svg`。完整品种表（含配色）：

**狗狗（dog）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `shiba` | 柴犬 | `#E8A33D` | `#FFF4E2` | `#F6C79B` | 耳:tri |
| `corgi` | 柯基 | `#EFAE72` | `#FFF8F0` | `#F8C79E` | 耳:tri |
| `pomeranian` | 博美 | `#F5CE8A` | `#FFF7E8` | `#FBE0B4` | 耳:tri |
| `samoyed` | 萨摩耶 | `#FFFBF2` | `#FFFFFF` | `#F1E4D2` | 耳:tri |
| `frenchie` | 法斗 | `#C6CEDA` | `#EDF2F7` | `#F3C9CB` | 花纹:mask/#5B6472，耳:bat |
| `dachshund` | 腊肠 | `#9A6238` | `#E9C7A0` | `#C08A54` | 耳:flop |
| `border` | 边牧 | `#FFFDF8` | `#FFFFFF` | `#5B6472` | 花纹:patch/#3C4250，耳:flop |
| `husky` | 哈士奇 | `#B9C4CE` | `#FFFFFF` | `#8E9AA6` | 花纹:mask/#3C4250，耳:tri |

**猫咪（cat）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `orange` | 橘猫 | `#F2A65A` | `#FFF0DC` | `#F8C99B` | 花纹:stripe/#E08C3C，耳:tri |
| `tuxedo` | 奶牛猫 | `#FFFDF8` | `#FFFFFF` | `#F3C9CB` | 花纹:patch/#3A3A44，耳:tri |
| `calico` | 三花 | `#FFF7EF` | `#FFFFFF` | `#F3C9CB` | 花纹:patch/#E08A3C，耳:tri |
| `black` | 黑猫 | `#43434F` | `#5A5A66` | `#8A7F86` | 耳:tri |
| `british` | 英短灰 | `#AEB7C2` | `#DDE3EA` | `#F3C9CB` | 耳:tri |
| `ragdoll` | 布偶 | `#F8F1E8` | `#FFFFFF` | `#F3C9CB` | 花纹:point/#8E7B6E，耳:tri |
| `siamese` | 暹罗 | `#EFE3CC` | `#FFF8EE` | `#8E7B6E` | 花纹:point/#5B4C43，耳:tri |

**仓鼠（hamster）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `golden` | 金丝熊 | `#F3C98B` | `#FFF3DF` | `#F8D9AC` | 耳:round |
| `line3` | 三线 | `#CBAE86` | `#F0E2CC` | `#E4CBA6` | 花纹:spot/#8B7355，耳:round |
| `pudding` | 布丁 | `#F7DC9E` | `#FFF6E3` | `#FBE7C0` | 耳:round |
| `silverfox` | 银狐 | `#EDEAE4` | `#FFFFFF` | `#DFD8CE` | 花纹:patch/#B9B4AC，耳:round |
| `robo` | 老公公 | `#D9C4A3` | `#F5EBD8` | `#EFE0C4` | 耳:round |

**荷兰猪（guineapig）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `shorthair` | 短顺 | `#E8C08A` | `#F7E4C6` | `#F3CFA6` | 耳:round |
| `longhair` | 长毛 | `#F0D9B5` | `#FFF1DC` | `#FBE7CC` | 耳:round |
| `tri` | 三花豚 | `#FFFDF8` | `#FFFFFF` | `#F0B7A8` | 花纹:patch/#E0A45C，耳:round |
| `white` | 纯白豚 | `#F7F2EA` | `#FFFFFF` | `#F0C7BE` | 耳:round |
| `black` | 黑豚 | `#5B534C` | `#7C7268` | `#C08A8A` | 耳:round |

**水豚（capybara）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `normal` | 水豚 | `#A98156` | `#C29A6B` | `#8E6B45` | 耳:tiny |
| `grey` | 灰豚 | `#8E8375` | `#A79C8D` | `#736A5E` | 耳:tiny |
| `caramel` | 焦糖豚 | `#C08B54` | `#D8A870` | `#A0713F` | 耳:tiny |
| `albino` | 白化豚 | `#E7D8C6` | `#F5EDE1` | `#CDBBA4` | 耳:tiny |
| `baby` | 小水豚 | `#B58E63` | `#CDA57A` | `#966F45` | 幼体，耳:tiny |

**鸭子（duck）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `yellow` | 小黄鸭 | `#FFE066` | `#FFF3C4` | `#FFE066` | 头色:#FFE066 |
| `white` | 白鸭 | `#FFFDF7` | `#FFFFFF` | `#FFFDF7` | 头色:#FFFDF7 |
| `call` | 柯尔鸭 | `#FFFDF2` | `#FFFFFF` | `#FFFDF2` | 头色:#FFFDF2，幼体 |
| `mallard` | 绿头鸭 | `#F2E7D2` | `#FFFBF0` | `#F2E7D2` | 头色:#3E6B4F |
| `black` | 黑番鸭 | `#4C4A52` | `#6A6874` | `#4C4A52` | 头色:#3B3941 |

**小马（pony）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `cream` | 奶油马 | `#F6E3C5` | `#FFF8EC` | `#F6E3C5` | 鬃毛:#E8CBA0，耳:tri |
| `sakura` | 樱花粉 | `#F7C6D9` | `#FFF0F5` | `#F7C6D9` | 鬃毛:#E79EBE，耳:tri |
| `sky` | 天青蓝 | `#C9DCEA` | `#EAF4FA` | `#C9DCEA` | 鬃毛:#A9CBE0，耳:tri |
| `pearl` | 黑珍珠 | `#52525E` | `#6E6E7C` | `#52525E` | 鬃毛:#3A3A46，耳:tri |
| `unicorn` | 独角兽 | `#F3E8FF` | `#FFFFFF` | `#F3E8FF` | 鬃毛:#FFC7E5，独角，耳:tri |

**松鼠（squirrel）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `red` | 红松鼠 | `#C96A3B` | `#E9A87F` | `#F0C0A2` | 耳:tuft |
| `grey` | 灰松鼠 | `#9AA0A6` | `#C9CDD2` | `#E2E5E8` | 耳:tuft |
| `snow` | 雪松鼠 | `#EDE7DC` | `#FFFFFF` | `#FAF6EF` | 耳:tuft |
| `flying` | 小飞鼠 | `#C4A484` | `#E4CDB2` | `#F2DCC2` | 耳:tuft |

**羊驼（alpaca）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `cream` | 奶白羊驼 | `#F5EBDD` | `#FFFBF4` | `#E4D6C2` | 耳:spike |
| `camel` | 驼色羊驼 | `#D8B48C` | `#F0DCC2` | `#C49E73` | 耳:spike |
| `choco` | 巧克力 | `#8B6B52` | `#A8876C` | `#6F5340` | 耳:spike |
| `galaxy` | 星空羊驼 | `#CFC2E8` | `#E9E1F7` | `#A896D4` | 耳:spike |

**小猪（pig）**

| 品种id | 中文名 | 主色 | 浅色 | 细节色 | 备注 |
|---|---|---|---|---|---|
| `pink` | 粉小猪 | `#F7B8C4` | `#FFD9E1` | `#F5A0B0` | 耳:tri |
| `spotted` | 小花猪 | `#FFFDF8` | `#FFFFFF` | `#F5A0B0` | 花纹:patch/#F0A8B8，耳:tri |
| `black` | 小黑猪 | `#5C5148` | `#7A6E64` | `#B49A94` | 耳:tri |
| `teacup` | 茶杯猪 | `#F2C9C0` | `#FFE8E3` | `#E8A79C` | 幼体，耳:flop |

## 批次 C —— 围栏与场景装饰

| 路径 | 内容 | 规格 |
|---|---|---|
| `assets/art/fence.svg` | 木质小栅栏（单个围栏外框，四边带木条） | viewBox 0 0 200 140，中间镂空 |
| `assets/art/sign.svg` | 围栏木牌（写动物名的地方，留白不写字） | viewBox 0 0 80 32 |
| `assets/art/poop.svg` | 便便（清扫用，圆润可爱不恶心） | viewBox 0 0 48 48 |
| `assets/art/barn.svg` | 谷仓（扩建/商店入口图标） | viewBox 0 0 120 120 |

## 批次 D —— UI 图标

全部 viewBox `0 0 48 48`，背景透明，线条粗一点（小尺寸下要认得出）。

| 路径 | 内容 |
|---|---|
| `assets/art/ui/coin.svg` | 金币（圆形带星星高光，暖金色） |
| `assets/art/ui/heart.svg` | 心情/爱心 |
| `assets/art/ui/full.svg` | 饱食度（叉勺或饭碗） |
| `assets/art/ui/level.svg` | 等级（小星星） |
| `assets/art/ui/exp.svg` | 经验值（闪电或上升箭头） |
| `assets/art/ui/broom.svg` | 清扫扫把 |
| `assets/art/ui/pet-hand.svg` | 抚摸（小手） |
| `assets/art/ui/lock.svg` | 未解锁围栏 |

## 批次 E —— 特效与气氛

| 路径 | 内容 |
|---|---|
| `assets/art/fx/heart-pop.svg` | 冒爱心（抚摸/开心） |
| `assets/art/fx/star-pop.svg` | 升级小星星 |
| `assets/art/fx/note.svg` | 音符（心情高时） |
| `assets/art/fx/zzz.svg` | 睡觉 Zzz |
| `assets/art/fx/sweat.svg` | 汗滴（饿了/不开心） |
| `assets/art/fx/sparkle.svg` | 闪光（传说品质出场） |

## 已有素材（不用再做）

```
assets/art/farm-meadow.svg            背景
assets/art/ground/*.svg               10 张围栏地面（wood cushion chips haybed onsen water pasture stump plateau mud）
assets/art/food/*.svg                 16 个食材：grass hay leaf carrot apple corn lettuce nut seed fish jerky milk pumpkin watermelon orange donut
assets/art/item/*.svg                 10 个产出：fur hairball seedstash hayball yuzu egg mane pinecone wool truffle
```

## 接入约定

- 素材放进对应路径即可生效，游戏里 `ART` / 贴图注册表按路径懒加载
- **缺文件不会报错**：会自动回落到程序化绘制（动物回落到 Canvas 手绘，图标回落 emoji）
- 所以**放心分批提交**，哪张没做完不会开天窗
- 建议一次提交一个批次，commit message 用 `art: 批次X - xxx`
