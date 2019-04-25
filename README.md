# Initial page

## 

## Can I become who I want to be?

That's a tough question but thankfully, our team is on it. Please bear with us while we're investigating.

## 逻辑题



* 给一串只包含0~9的数字串，每个数字出现的概率相同（比如32978417506），现在告诉你（1,3,5,7）这四个数字不可用，即只能用（0,2,4,6,8,9）这6个数，如何表示原数字串？
  * 00表示0, 02表示1, 04表示3， 06表示5， 08表示7
  * 15位表示以前的10位，所以存储多出来0.5倍
* 凸包问题：求包裹所有点的凸多边形
  * 穷举法O\(n³\)
    * 思路：两点确定一条直线，如果剩余的其他点都在这条直线的一侧，则这两个点是凸包上的点，否则就不是。
    * 步骤：1.将点集里面的所有点两两配对，组成 n\(n-1\)/2 条直线。2.对于每条直线，再检查剩余的n-2个点是否在直线的同一侧。
    * ![](.gitbook/assets/image%20%283%29.png)
    * 结果为正时则\($$x\_3, y\_3$$\)在直线左侧，为负在右侧
  * 分治法O\(nlogn\)
    * 思路：找到凸包点，分割点集，在子点集上继续找凸包点
    * * * 步骤：
      * 找到横坐标最大的P1和P2肯定是凸包点，分割为上下包
      * 对上包，求**距离直线最远的点（公式如上）**，即图中Pmax
      * 把P1Pmax的左侧和PnPmax的右侧当上包
      * 重复第二三步，对下包也这样
  * 步进法O\(nH\)
    * H是闭包点的个数。
    * 思路：
      * ![](https://lbgzmhl.gitbooks.io/microsoft-suzhou-interview/content/assets/%E6%AD%A5%E8%BF%9B%E6%B3%95.png)
      * 先找纵坐标最小的点加入闭包
      * 从P0开始，逆时针找点集上使alpha角\(和x轴夹角\)最小的点，即P1
      * 从P1出发，逆时针找点集上使alpha角\(P0P1和P1P?夹角\)最小的点，即P2
      * 重复，直到回到P0。注意共线时点都加入闭包，但选最远点为下一次的出发点。
  * Graham扫描法O\(nlogn\)
    * ![](https://lbgzmhl.gitbooks.io/microsoft-suzhou-interview/content/assets/20150530145453912.gif)



