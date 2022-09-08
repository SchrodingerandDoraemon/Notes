# OOD (object orientied design)

## Basic Knowledge

面试时间应该是一小时，但是会先问我behavior question， 然后再问OOD，所以OOD的时间可能是30-45mins

### 思路(Steps)：

1. Clarify: 这部分我们一起完成，你可以打字我帮你问，主要是问面试官的需求。
2. core object: 写出一些关键的object 和他们的 field （变量），这个时候可以用上interface（可以做一个暴露在外面的接口， 比方说 interface： Elevator 和 具体实现类：ElevatorImpl） and abstract class and enum.
3. Use cases： 想一下use case然后可以在interface 里面写上 主要的use case 的method
4. 然后去填充implement interface的 class 的method，一边填充一边解释为什么要这么设计， 填充到面试官满意. All done！

***It's not nessecary to complete all the code, but just have structure the design and some core implementation. Only the some part of code is need to be completed, ask interviewer which part.***

### ***几个design的时候需要注意的原则：***

1. Solid principles

2. Design pattern(Singleton, factory pattern etc, stragegy pattern. Design pattern is rarely used in interview becasue of limited time, but it would be critical to just mention it to Interviewer. for example: "here we can also use stragegy pattern to replace the if else")

3. 运用面向对象的封装啊之类的。Use enum + interface + constants to show off the best practice of industury. (must have)

### ***some video for learning:***

https://www.bilibili.com/video/BV1Xa411Y7aG?spm_id_from=333.999.0.0

https://www.bilibili.com/video/BV1C5411R7EF?spm_id_from=333.999.0.0&vd_source=7bf5b3de1821dcc77df12868e01d369f

https://www.bilibili.com/video/BV1WF41177fv?spm_id_from=333.999.0.0&vd_source=7bf5b3de1821dcc77df12868e01d369f

https://www.bilibili.com/video/BV1HU4y1q7vB?spm_id_from=333.337.search-card.all.click&vd_source=7bf5b3de1821dcc77df12868e01d369fwas


-------------------

## ***几个看答案和面试题的好地方***:

https://leetcode.com/discuss/interview-question/object-oriented-design?currentPage=1&orderBy=hot&query=

https://www.lintcode.com/problem/?typeId=10

youtube 和 bilibili 也有很多教程。

https://github.com/ycwkatie/OOD-Object-Oriented-Design  : 有每个题的class diagram，但没有implementation.


-------------------

## ***High frequency questions (ordered by frequency)***:

OOD的题没有标准答案，要求逻辑合理和注重面向对象的design。题目也要问面试官的具体需求，每个人都不一定一样。


### ***第一题（Design Linux find command）出现的频率远多于其他。23题也出现过多次，其他题目在面经里都是孤例。***

#### ***Design Linux find command***: 
面经：

要求给定一个directory，要筛选出符合条件的file，例如大于1MB的所有文件，或后缀名为.xml的文件. 实现cd ./功能，即返回当前文件夹的上一级。实现list_all_files功能，给定1个文件夹，递归搜索到所有子文件夹内的文件，返回1个列表.

比如给你 /home/user 以及找不能超过5MB的文件大小，后缀是.java等条件。实现查找返回所有该directory下面符合要求的文件。假设已有class File, isDirectory(), getSize(), listOfSubDirector()之类。经过讨论明确如果File是个文件夹， isDirectory()返回true, 且listOfSubDirector()返回该文件夹下所有文件夹及文件。如果File是文件， isDirectory()返回false, 且listOfSubDirector()返回null。我一开始还以为先从root出发，把 “/home/user” 用split.("/")去找到当前directory，国人老哥说输入已给你定位好那个文件夹。那就简单的对这个文件夹做一个DFS即可。follow up : 使这个查找功能具有良好的扩展性。给定interface { public boolean match();} 讨论下，其实就是先根据自己想要什么条件就自己先implements这个接口， 然后将原来的搜索method的传入参数改成所需查找条件的class即可。
  
reference solution：

https://leetcode.com/discuss/interview-question/369272/Amazon-or-Onsite-or-Linux-Find-Command

https://leetcode.com/discuss/interview-question/609070/Amazon-OOD-Design-Unix-File-Search-API

https://blog.csdn.net/u013325815/article/details/108217340

https://mkyong.com/java/search-directories-recursively-for-file-in-java/

#### ***Design Amazon locker （就是国内的那种取快递的寄存柜, locker有大中小三种尺寸。）***

https://leetcode.com/discuss/interview-question/system-design/233869/Design-Amazon-Locker-system

第三轮高冷意大利老哥：
全程我说一句话要过10~30秒才回。
OOD: 有好几个储物柜和亚马逊的包裹，设计模拟把包裹装到储物柜的过程。经过很长时间的讨论给你包裹和储物柜都有大小，你想要找到刚好能塞得下的储物柜，一个柜子只能赛一个之类的， 题目描述里不明确的、需要和面试官讨论的很多。
我直接把储物柜表示成size的array，sorted by size. 且再加个boolean[]表示是否已经塞了东西，在class的constructor输入每个柜子的size。每个包裹进来直接从头开始扫到第一个非空的就是刚好塞得下的。又讨论了下，他说又想要拿回某个包裹的功能，那么就用HashMap<pacakge, index>即可。
他说能不能优化， 我说可以用稍作修改的binary sear‍‌‍‍‌‍‍‍‌‍‌‌‌‍‌‍‌‍‌ch，先找到第一个比包裹size大的Index，再开始扫，找第一个空的柜子。然后实现了。
问复杂度：worst case仍然是O(N),但改进了average time complexity.
还问能不能不用boolean[]表示柜子满了啊？（我到现在还不知道这个follow up问的有什么意义）我会错意了，然后过一会时间就到了。
最后聊天完我更想打他了。


#### ***Design  elevator***

https://medium.com/geekculture/system-design-elevator-system-design-interview-question-6e8d03ce1b44

https://leetcode.com/discuss/interview-question/object-oriented-design/846057/Amazon-or-OODElevator-System-with-N-elevators./726511

https://leetcode.com/discuss/interview-question/124660/design-an-Elevator

https://leetcode.com/discuss/interview-question/1612174/OOD-Elevator


#### ***剩下的其他面经，其他面经，我整理了就这么多，内容有限。。抱歉啦：***

design a  centralized logging service

OOD , 向用户推荐他没买但是他朋友买了的商品

Lottery Question

design web page render

titactoe........估计接到之前两轮的反馈了直接让我自生自灭算了。。。算写完了，没到follow up：要求这个游戏有自己随机填的能力和不只是接受下一个指令而是一系列来自不同玩家的指令的能力。

系统设计 一个hit counter

OOD是design coupons system
basic requirement: 1. admin able to create rules / active/deactive coupns. 2. user able to check the rules of coupons, check availability to use coupon...

设计一个文件打印/储存/上传服务，重点考察factory pattern

coding让design了一个org chart empl‍‌‍‍‌‍‍‍‌‍‌‌‌‍‌‍‌‍‌oyee class， 先让你计算树的高度，然后让你遍历一下树算平均工资...感觉是easy题？

设计一个系统，输入产品名称，返回过去一周总销售排名和所属category中的排名。每时每刻的sales都要算进去，原谅我见识少，不知道怎么处理数据库。

设计一个好书推荐的应用，这个应用会连接亚马逊，获取用户对每本书的打分（重点问）。
回答：数据库内保存subscriber-publis‍‌‍‍‌‍‍‍‌‍‌‌‌‍‌‍‌‍‌her的关系，亚马逊每隔1小时会将这1小时内最新的打分发送到我的系统。
系统分为collection service和query service，前者负责接收数据，存到数据库，同时每隔一段时间更新query service连接的缓存。query service则用来供用户查询。
Followup：如果亚马逊的系统（source_of_truth）出问题了怎么办？

第四轮，白人小哥，BQ25分钟左右。OOD，设计一个thermostat，input会给你一个2d array‍‌‍‍‌‍‍‍‌‍‌‌‌‍‌‍‌‍‌代表房屋房间结构。要求能够给某个房间设定温度，然后设定温度的function要求能够return到达指定温度所需的时间（给了一个计算所需时间公式）。FUQ是再写一个得到某个房间现在温度的function，如果正在加热或制冷，那么就假设温度随时间线性增加、减少。没时间写码了，大概说了说思路。

设计吃鸡游戏

OOD, install package，1 1 需要写topology sor‍‌‍‍‌‍‍‍‌‍‌‌‌‍‌‍‌‍‌t，类似二姨玲

题目是 OOD，设计 prime video 搜索服务。follow up 是让自己写代码调用自己写的 API 并口述测试。

