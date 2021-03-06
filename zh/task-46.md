这次我们不是要编写一个与 **井字棋** 游戏竞争对手，而是要编写这种算法的重要组成部分 - 检测函数，这个检查函数可以告诉我们游戏是否结束以及哪一方胜出。

这个游戏运行在一个 `3 x 3` 大小的平面上。让我们假设每个栅格用以下方式命名：

     1 | 2 | 3
    ---+---+---
     4 | 5 | 6
    ---+---+---
     7 | 8 | 9

两个玩家轮流将他们的分数（ `X` 表示第一位玩家 `O` 表示第二位玩家）放到剩余的任意栅格中，其中一个玩家首先完成 3 连线（三个 X 或 三个 O）后就立即获胜。三连线可以是行、列、对角线的形式（一个有 8 种形式），假如执行了如下的操作：

    X   O
    -------
    7
        5
    4
        1
    9
        2
    8

这回导致形成如下的栅格位置：

     O | O |  
    ---+---+---
     X | O |  
    ---+---+---
     X | X | X

从而第一个玩家（X）首先完成三连线获胜。

## 问题陈述

你会接收一个操作动作的序列（假如总是 `X` 首先移动） - 通过序列中的数字来标记其放置的对应的栅格 - 你的任务就是确认在哪一步操作后第一个三连线（以任意形式）出现。

**输入数据** 第一行显示的是测试案例个数。

接下来每行包含一个测试案例 - 每行有 9 个数字，依次描述操作那个栅格。

**答案** 应该包含其中一个玩家获胜时双方一共走了多少步棋（用 `1` 来标示），如果走到最后游戏也没有赢家就用 `0` 标示。

举个栗子：

    输入数据:
    3
    7 5 4 1 9 2 8 3 6
    5 1 3 7 6 4 2 9 8
    5 1 2 8 6 4 7 3 9

    答案:
    7 6 0

