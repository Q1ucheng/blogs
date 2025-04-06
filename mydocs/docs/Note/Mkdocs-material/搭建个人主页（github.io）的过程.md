# 搭建个人主页（github.io）的过程

> 逛知乎时发现有很多正在申请更高学位的答主们都有一个类似于自我简介的个人网站，我虽然很早之前就创建了 q1ucheng.github.io/blogs 这个静态页面来存放一些学习记录，但似乎不太能起到让人快速了解我的基本情况的作用（内容过于离散），于是开始新建一个更简明的个人网站，同时也能在编写个人简介的过程中梳理自己本科两年多都有哪些收获

相较于我之前做的基于 **mkdocs-material** 的网站，这个新网站的构建和部署就显得非常简单，只需要写好`index.html`push到远程仓库中即可：

[:simple-github: Source Code](https://github.com/Q1ucheng/Q1ucheng.github.io){ .md-button }

网站的主要内容包括：

- 个人简介（教育经历，兴趣爱好）
- 感兴趣的研究方向
- 所获荣誉奖项
- 修读课程情况（本科主修专业课成绩，自学公开课记录）

但发现一个问题，电脑端查看时排版正常，但是移动端就显示错位，看来需要对移动端进行适配，询问GPT告诉我可以这样配置：

```css
/* 媒体查询，当屏幕宽度小于等于768px时应用以下样式 */
        @media (max-width: 768px) {
            body {
                padding: 20px; /* 减少页面的左右内边距 */
                font-size: 18px; /* 减小字体大小 */
            }

            header {
                flex-direction: column; /* 垂直排列导航栏元素 */
                padding: 20px;
                margin: -20px -20px 20px -20px;
            }

            nav ul li {
                display: block; /* 让导航链接垂直排列 */
                margin: 10px 0;
            }

            .main-container {
                flex-direction: column; /* 垂直排列主要内容 */
            }

            .left-section {
                width: 100%; /* 让左侧部分占满宽度 */
            }

            .name {
                font-size: 2.5em; /* 减小名字的字体大小 */
            }

            .awards-section,
            .teaching-section {
                padding: 0 20px; /* 减少奖项和教学部分的左右内边距 */
            }
        }
```

也就是利用CSS媒体查询针对不同设备进行格式调整，过程中也发现在浏览器（Edge等）中打开`index.html`，右键检查，左上角会有专门用于模拟移动端的小工具，这样就可以及时地看到添加适配后的网站效果了

