# ./src 摘录于 [github-snabbdom](https://github.com/snabbdom/snabbdom)

> 总结: vue 数据驱动视图 --> vdom模拟dom的数据结构 --> diff算法找出最小变更 --> dom操作最少

- h 函数相当于 render 函数，生成 vnode

- vnode 的数据结构类似于上一节用JS模拟的DOM结构

- patch 函数会比较新旧vnode，计算出最小的更新范围，最后更新DOM

- 体会 diff 算法如何优化dom操作

- 体会 key 的重要作用

```
patch --> patchVnode  -----------> updateChildren ( 首尾指针同时向中间靠拢遍历，减少一半循环 )

              --> addVnodes               --> sameVnode ( selector & key )
              --> removeVnodes            --> insertBefore ( key )
```

![](https://s1.ax1x.com/2020/05/07/YeZO1O.png)

![](https://s1.ax1x.com/2020/05/07/Yeecbd.png)
