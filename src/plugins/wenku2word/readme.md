# 百度文库转 Word / PDF | 免费下载百度文库文章 [![gitee.png](https://palerock.cn/api-provider/files/view?identity=L2FydGljbGUvaW1hZ2UvMjAyMDA2MjkxNTQyMTMwNzVXcWZyU2dTbC5wbmc=&w=20)](https://gitee.com/HGJing/everthing-hook/tree/master/src/plugins/wenku2word "Gitee")  [![github.png](https://palerock.cn/api-provider/files/view?identity=L2FydGljbGUvaW1hZ2UvMjAyMDA2MjkxNjU3NDkzMDkybWNLRXhHMi5wbmc=&w=20)](https://github.com/canguser/hooker-js/tree/master/src/plugins/wenku2word "Github")

![Daily Installs](https://palerock.cn/node-service/images/greasyfork/views-info/405373)
![Daily Installs](https://palerock.cn/node-service/images/greasyfork/stats/daily-installs/405373)
![Daily Updates](https://palerock.cn/node-service/images/greasyfork/stats/daily-updates/405373)
![Total Installs](https://palerock.cn/node-service/images/greasyfork/stats/total-installs/405373)

不同于其它的文库下载器，该插件原理是使用脚本将文库的文本内容找到并整理格式最后转换为 word / PDF 下载，使用该脚本不会将页面跳转到其它网址，也不会有任何收费选项，只需要等待解析完成即可，**如有问题请多多反馈**

使用方法如下：

1. 安装: [GreasyFork](https://greasyfork.org/scripts/405373)
2. 进入指定文库页面
3. 等待页面加载完毕
4. 在下载按钮中找到「文库转 Word / PDF 」按钮 （如最后图所示）
5. 点击按钮后根据提示等待下载

注意事项

- 转 Word 时
    1. 目前只支持转换文字内容
    2. 目前只支持没有阅读限制的文章（只要没有阅读限制，无论是用券、VIP或付费文章都能下载）

- 转 PDF 时
    1. 可以转换图片，格式会大幅度保留
    2. 但是转换后的 PDF 内容不能复制

> 提示： 不能通过转 Word 下载 PPT 或者图片，如果为空文档，检查该文档是否全是图片

更新日志

- 2022-01-27 [0.0.7] 修改部分文字表达
- 2022-01-27 [0.0.6] 支持转换 PDF 功能啦
- 2022-01-21 [0.0.5] 修复文档页面由于使用 canvas 导致的无法提取文字的问题
- 2021-08-24 [0.0.4] 修复某些文库链接插件没有加载的问题
- 2021-05-24 [0.0.3] 修复文库更新后按钮样式再度不显示的问题
- 2021-01-25 [0.0.2] 修复文库更新后按钮样式不显示的问题
- 2020-06-15 [0.0.1] 公测第一版，包含基础功能