# 时间结界

适用于 Mindustry 160.5 的纯加速建筑模组，使用原版 `OverdriveProjector`，无需脚本或编译。

## 在游戏中安装

1. 打开“模组 → 导入模组 → 从 GitHub 导入”。
2. 输入 `ZYCEDU/time-barrier`。
3. 下载完成后按提示重启游戏。
4. 在建造菜单的“效果”分类中找到“时间结界”。建筑默认解锁；可先在塞普罗环境的沙盒地图测试。

## 建筑属性

| 属性 | 数值 |
| --- | --- |
| 生命值 | 10000 |
| 尺寸 | 1×1 格 |
| 基础建造时间 | 1 秒 |
| 建造材料 | 铜、铅、钛、钍各 100 |
| 加速半径 | 30 格，圆形范围 |
| 总速度倍率 | 10 倍，即 1000% 总速度，游戏可显示为 +900% |
| 电力、物品、液体需求 | 无 |

建筑只提供加速功能，没有发电和护盾。

## 使用规则

- 只作用于可超速的己方建筑；沿用原版投影器的范围判定。
- 建成后有原版投影器的短暂预热及刷新间隔。
- 目标建筑仍需具备其自身要求的电力、原料和输出空间。
- 多个投影器采用较高倍率，不相乘叠加。
- 不能超速的建筑及单位移动速度不受影响；结界自身不能被超速。
- 1 秒为基础建造时间，实际施工速度受建造单位和地图规则影响。

## 自己修改

编辑 [`content/blocks/time-barrier.json`](content/blocks/time-barrier.json)：

- `health`：生命值。
- `buildTime`：基础建造时间，60 对应 1 秒。
- `range`：内部距离单位，240 对应 30 格。
- `speedBoost`：总倍率，10 对应 10 倍。
- `requirements`：建造材料。

修改并提交后，在游戏中更新模组并重启。

## 验证

已在官方 Mindustry 160.5 无界面引擎中验证文件导入，并通过 31 项功能检查，包括属性、范围、己方与敌方区分、持续无资源运行、启停、倍率叠加和存档恢复。尚未在用户安卓平板上实测。

参考：[官方模组指南](https://github.com/MindustryGame/wiki/blob/master/docs/modding/1-modding.md)、[160.5 原版超速投影器实现](https://github.com/Anuken/Mindustry/blob/v160.5/core/src/mindustry/world/blocks/defense/OverdriveProjector.java)。
