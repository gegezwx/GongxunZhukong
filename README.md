# 工程训练赛智能物流赛道主控

## 1. 硬件设计框图



![](https://gegeekblog-1325046062.cos.ap-chengdu.myqcloud.com/blogSTM32F407VET6%E4%B8%BB%E6%8E%A7%E6%9D%BF.png)

## 2. Layout

![](https://gegeekblog-1325046062.cos.ap-chengdu.myqcloud.com/blog20240328124831.png)

## 3. 总结以及不足

1. 由于外壳限制，限定死了排针板框以及排针位置，但是电源部分集中在右上角且过于紧凑，会有美观问题以及积热问题，可以考虑分散一点电源放置

2. 电源部分电感下铺铜且走线，这是很大的问题，然而我当时竟然没有在意，经过学习b站上各种视频讲解觉得可以做以下改进

   ![](https://gegeekblog-1325046062.cos.ap-chengdu.myqcloud.com/blog20240328125027.png)

   1. [【销量最高的开关电源芯片：德州仪器TPS5430降压电路 产生负电压 开关电源PCB设计 降低纹波与噪声 输出电容的选型,TPS5450，长江大学，唐老师讲电赛】 ](https://www.bilibili.com/video/BV1sw411j7Nz/?share_source=copy_web&vd_source=c34265eabafe1cdd353228c94e5b1881)参考以上学习视频

   2. 芯片手册参考布局![](https://gegeekblog-1325046062.cos.ap-chengdu.myqcloud.com/blogPasted%20image%2020240128230412.png)

   3. 唐老师参考布局 

      ![](https://gegeekblog-1325046062.cos.ap-chengdu.myqcloud.com/blogPasted%20image%2020240310190547.png)

   4. 注意要点

      1. 输入输出都要有大容量和小容量电容并联，且Co大容量更接近芯片Ci小容量接近引脚
      2. 肖特基二极管以及输入输出电容的地需要尽量快的引入地平面，他们带来的干扰是很大的

