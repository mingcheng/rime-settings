# Rime 鼠须管输入法傻瓜式配置指南
  OS: macOS 10.14.6, Windows 10 LSTC 2019
  
  version: 0.14.0
  
  Date:2020-04-04
  
  ----
  
  折腾了一下 Rime 输入法，系统输入法太难用了。输入界面:

  **macOS**

  ![macOS](https://wang-1258168870.cos.ap-guangzhou.myqcloud.com/pic/2019-10-11-RoMhx5.png)

  **win 10**

  ![win 10](https://wang-1258168870.cos.ap-guangzhou.myqcloud.com/rLU5Ff.png)

  目录
=================

* [更新记录](#%E6%9B%B4%E6%96%B0%E8%AE%B0%E5%BD%95)
* [用法](#%E7%94%A8%E6%B3%95)
* [配置文件说明](#%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E8%AF%B4%E6%98%8E)
* [全拼用户](#%E5%85%A8%E6%8B%BC%E7%94%A8%E6%88%B7)
* [几个你可能会关注的问题](#%E5%87%A0%E4%B8%AA%E4%BD%A0%E5%8F%AF%E8%83%BD%E4%BC%9A%E5%85%B3%E6%B3%A8%E7%9A%84%E9%97%AE%E9%A2%98)
  * [1、怎么修改输入法皮肤？](#1%E6%80%8E%E4%B9%88%E4%BF%AE%E6%94%B9%E8%BE%93%E5%85%A5%E6%B3%95%E7%9A%AE%E8%82%A4)
  * [2、编辑拓展词库？](#2%E7%BC%96%E8%BE%91%E6%8B%93%E5%B1%95%E8%AF%8D%E5%BA%93)
  * [3、怎么添加自造词？](#3%E6%80%8E%E4%B9%88%E6%B7%BB%E5%8A%A0%E8%87%AA%E9%80%A0%E8%AF%8D)
  * [4、emoji 的相关问题](#4emoji-%E7%9A%84%E7%9B%B8%E5%85%B3%E9%97%AE%E9%A2%98)
  * [5、如何让鼠须管在软件中默认英文？](#5%E5%A6%82%E4%BD%95%E8%AE%A9%E9%BC%A0%E9%A1%BB%E7%AE%A1%E5%9C%A8%E8%BD%AF%E4%BB%B6%E4%B8%AD%E9%BB%98%E8%AE%A4%E8%8B%B1%E6%96%87)
  * [6、如何自定义符号上屏情况？](#6%E5%A6%82%E4%BD%95%E8%87%AA%E5%AE%9A%E4%B9%89%E7%AC%A6%E5%8F%B7%E4%B8%8A%E5%B1%8F%E6%83%85%E5%86%B5)
* [如果你有其他问题，请开 issue，附上你的系统版本。](#%E5%A6%82%E6%9E%9C%E4%BD%A0%E6%9C%89%E5%85%B6%E4%BB%96%E9%97%AE%E9%A2%98%E8%AF%B7%E5%BC%80-issue%E9%99%84%E4%B8%8A%E4%BD%A0%E7%9A%84%E7%B3%BB%E7%BB%9F%E7%89%88%E6%9C%AC)
* [已知问题](#%E5%B7%B2%E7%9F%A5%E9%97%AE%E9%A2%98)
* [To do](#to-do)
* [参考/致谢](#%E5%8F%82%E8%80%83%E8%87%B4%E8%B0%A2)


  ## 更新记录
  - 2020.03.31 主要问题修复，在 macOS Majave 上测试没有「大BUG」
  - 2020.04.01 感谢 [@mingcheng](https://github.com/mingcheng) 提供的词库
  - 2020.04.02 上传了 Windows 的配置文件，经试验，macOS 皮肤的有些特性不支持，于是只加（chao）了一个 win10 输入法皮肤，有个性化需求的用户请自己定制（定制指南见后）
  - 2020.04.04 1、删掉了`luna_pinyin.dict.yaml`，其中有些词库有点问题（删掉好像没啥影响），如打“复制”一词，无效;2、优化了部分符号上屏情况，增加了逗号句号翻页的功能。依然感谢 [@mingcheng](https://github.com/mingcheng)

  -----


  
  ## 用法
  1. 安装Rime输入法,并注销或重启
  2. 下载仓库所有配置文件到本地
  3. 安装字体文件(font 文件夹内的两个文件)
  4. 右上角打开用户设定，会弹出用户设定文件夹
  
  ![](https://wang-1258168870.cos.ap-guangzhou.myqcloud.com/pic/2019-10-11-1lAuOL.png)
  
  5. 将下载的除字体外的所有文件覆盖到用户设定文件夹
  
  6. 右上角菜单栏点击鼠须管图标，点击重新部署，部署完毕即可用
  
  
  ## 配置文件说明
  - `default.custom.yaml` 设置输入法、如何切换输入法、翻页等
  - `double_pinyin_flypy.custom.yaml` 双拼方案，我用的是小鹤双拼
  - `squirrel.custom.yaml` 设置哪些软件默认英文输入，输入法皮肤等
  - `custom_phrase.txt` 设置快捷输入，修改完成后要重新部署才能生效
  配置文件中大部分都有注释。

  ## 全拼用户
  Mac 用户使用 <code>Ctrl + &#96;</code> (`Tab`上面那个),切换至拼音那一项
  
  表情显示有问题参见：
  * [4、emoji 的相关问题](#4emoji-%E7%9A%84%E7%9B%B8%E5%85%B3%E9%97%AE%E9%A2%98)
  
  注意更改快捷输入对应的全拼内容

  ----

  ## 几个你可能会关注的问题
  ### 1、怎么修改输入法皮肤？
  `squirrel.custom.yaml` 文件，写了简单的注释。

  如果看不懂，请参考 https://mritd.me/2019/03/23/oh-my-rime/ 第四部分

  ### 2、编辑拓展词库？
  将词库文件拷贝到文件夹，修改 `luna_pinyin.extended.dict.yaml`文件

  将词库名字加在 `import_tables` 下(注意格式)

  重新部署即可

  **默认没有启用那么多的词库，如有需要请至上述文件中取消注释即可**
  
  ### 3、怎么添加自造词？
  添加至`custom_phrase.txt`文件中
  
  需要注意，输入的字母和汉字之间是 `tab`，而不是空格
  
  所以请使用不会自动替换`tab`为空格的编辑器修改此文件

  ### 4、emoji 的相关问题
  **emoji 显示方块**：下载除字体外的所有文件，然后重新部署，eomji 字符文件都在 `opencc` 文件夹中。

  **emoji 不显示**：<code>Ctrl + &#96;</code> (`Tab`上面那个)选“中/Y/半/汉"（可能是“中/N/半/汉"），第三项对应的是 emoji 的开关（可能指示的不准确），切换一下开关即可。

  **不需要 emoji**：同**emoji 不显示**，emoji 开关切换一下即可

  **已知 windows 显示的表情是黑白的，没有办法解决。**

  *如果彻底不需要表情，修改`default.custom.yaml`，`double_pinyin_flypy.custom.yaml`和`luna_pinyin.custom.yaml`（有注释）*

  ### 5、如何让鼠须管在软件中默认英文？
  在`/User/你的用户名/Library/Preferences/`中找到你需要添加的软件名称

  `squirrel.custom.yaml`文件中`app_options`下，照葫芦画瓢添加

  重新部署

  ### 6、如何自定义符号上屏情况？
  按下标点按键后，希望上屏哪些字符。在`double_pinyin_flypy.custom.yaml`文件中`punctuator`部分

  参照`symbols.yaml`修改(不建议直接修改`symbols.yaml`)


  ## 如果你有其他问题，请开 issue，附上你的系统版本。

  -----

  ## 已知问题
  - ~~**中文状态下，无法打出「-」**~~
  **已解决**
  
  有此问题的，替换`double_pinyin_flypy.custom.yaml`和`double_pinyin_flypy.schema.yaml`

  - **windows 输入法皮肤部分特性不支持**
  - **windows emoji 黑白无彩色**


  -----

  ## To do
  下一步计划重新做词库，将最新的热词更新一些进去。

  词库数量太大会拖慢输入法速度，如无必要，不准备添加长句进词库中。

  **如果有大佬有比较好的建议或现成词库，欢迎提 issue 或提 PR**

  
  ------
  
  ## 参考/致谢
  1. [Mac 下调校 Rime](https://mritd.me/2019/03/23/oh-my-rime/)
  2. [鼠须管 0.11 Mac 升级重装配置 2019](https://github.com/cnfeat/Rime)
  3. [鼠须管配置 2019](https://placeless.net/blog/rime-squirrel-customization-2019#article)
  4. [Schema.yaml 詳解](https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md)
  
  
