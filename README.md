# Algorithm-JiuZhang-Basic-03-Dynamic-Programming
九章算法基础班 - 动态规划

- 动态规划两种实现方法
  - 多重循环(自底向上/自顶向下)
    - 优点：正规，大多数面试官可以接受，存在空间优化可能性。
    - 缺点：思考有难度。
  - 记忆化搜索
    - 优点：容易从搜索算法直接转化过来。有的时候可以节省更多的时间。
    - 缺点：递归。

- 什么情况下使用动态规划？
  - 满足下面三个条件之一, 则极有可能是使用动态规划求解
    - 求最大值最小值
    - 判断是否可行
    - 统计方案个数

- 什么情况下不使用动态规划？(极不可能使用动态规划求解)
  - 求出所有具体的方案而非方案个数
  - 输入数据是一个集合而不是序列
  - 暴力算法的复杂度已经是多项式级别
    - 动态规划擅长与优化指数级别复杂度(2^n,n!)到多项式级别复杂度(n^2,n^3)
    - 不擅长优化n^3到n^2
    
- 动规四要素
  - 状态 State
    - 灵感，创造力，存储小规模问题的结果
  - 方程 Function
    - 状态之间的联系，怎么通过小的状态，来算大的状态
  - 初始化 Initialization
    - 最极限的小状态是什么, 起点
  - 答案 Answer
    - 最大的那个状态是什么，终点

- 面试中常见的动态规划类型
  - 坐标型动态规划 15%
  - 序列型动态规划 30%
  - 双序列动态规划 30%
  - 划分型动态规划 10%（算法强化班）
  - 背包型动态规划 10% （算法强化班）
  - 区间型动态规划 5% （算法强化班）

### 坐标型动态规划

- [triangle](https://www.lintcode.com/problem/triangle/description)

- [minimum-path-sum](https://www.lintcode.com/problem/minimum-path-sum/description)
  - state: f[x][y]从起点走到x,y的最短路径
  - function: f[x][y] = min(f[x-1][y], f[x][y-1]) + A[x][y]
  - intialize: f[i][0] = sum(0,0 ~ i,0) f[0][i] = sum(0,0 ~ 0,i)
  - answer: f[n-1][m-1]
