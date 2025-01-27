# JD_SHOPPER <img src="./Docs/img/shopper.svg" width="50px">

[![version](https://img.shields.io/badge/python-3.4+-blue.svg)](https://www.python.org/download/releases/3.4.0/)
[![status](https://img.shields.io/badge/status-stable-green.svg)](https://github.com/tychxn/jd-assistant)
[![license](https://img.shields.io/badge/license-GPL-blue.svg)](./LICENSE)
[![star, issue](https://img.shields.io/badge/star%2C%20issue-welcome-brightgreen.svg)](https://github.com/tychxn/jd-assistant)

[🇨🇳 中文](./README.md) |  [🇺🇸 English](./README.en.md)

京东抢购助手

1.缺货上架自动加购物车下单

2.定时加购物车下单

![操作界面](./Docs/img/banner.jpg)

## 主要功能

- 开箱即用的软件（仅windows）
- web操作界面（跨平台）
- 登陆京东商城（[www.jd.com](http://www.jd.com/)）
    - 手机扫码登录
    - 保存/加载登录cookies (可验证cookies是否过期)
- 商品查询操作
    - 提供完整的[`地址⇔ID`](./area_id/)对应关系
    - 根据商品ID和地址ID查询库存
    - 根据商品ID查询价格
- 购物车操作
    - 清空/添加购物车 (无货商品也可以加入购物车，预约商品无法加入)
    - 获取购物车商品详情
- 订单操作
    - 获取订单结算页面信息 (商品详情, 应付总额, 收货地址, 收货人等)
    - 提交订单（使用默认地址）
- 其他
    - 商品预约
    - 用户信息查询

## 近期更新

[查看详细日志](./Docs/change-log.md)

### V1.2.1

- 迁移架构到 `Turbon` *`v1.1.0-beta`*
- 修复 `HTTP Server` 字节丢失问题
- 自动检查并安装依赖
- `UI` 新增退出程序功能
- `UI` 新增检查运行状态
- 修复自动检查依赖不生效的问题
- 发布新版UI，修复若干UI打包问题

### V1.1.2

感谢 [@consults](https://github.com/consults) 与 [@malavinta](https://github.com/malavinta) 以及 [@uxgnod](https://github.com/uxgnod) 三位小伙伴对本项目的贡献

- 修复ui界面为+8时区
- 上线 README English Version
- 修复MacOS系统下图片显示不正常

### v1.1.1

感谢 [@laodiaoyadashu](https://github.com/laodiaoyadashu) 与 [@YuTao0310](https://github.com/YuTao0310) 对本项目的贡献

- 修复有货商品一直提示等待上架
- 修复用户名太长时，cookie不能正确创建
- 去除无用函数，修复错误函数参数

### 即将到来

- Docker镜像
- 在线地址选取
- 价格低于设定值自动下单功能
- 秒杀抢购功能

## 特别声明:

使用本仓库之前**必须阅读** -- [*使用须知*](./Docs/notice.md)
> ***您使用或者复制了本仓库且本人制作的任何代码或项目，则视为`已接受`此声明，请仔细阅读***  
> ***您在本声明未发出之时点使用或者复制了本仓库且本人制作的任何代码或项目且此时还在使用，则视为`已接受`此声明，请仔细阅读***

## 快速开始

### 通过 *windows程序* 运行
>  [点击通过Gitee下载压缩包(推荐)](https://gitee.com/louisyoungx/jd-shopper/attach_files/1001096/download/jd-shopper.zip)
> 
>  [点击通过GitHub下载压缩包](https://github.com/louisyoungx/jd-shopper/releases/download/v1.2.1/jd-shopper.zip)
1. 到release界面下载jd-shopper.zip包
2. 解压后在jd-shopper目录找到jd-shopper.exe文件
3. 点击运行，或者右键生成快捷方式后运行
4. 到 `/TEST/area_id/` 目录下查询你所在地的地区标识ID

> 注意：安装路径中不能有中文字符🚫
> 
> 比如 `C:/Users/someone/test/jd-shopper/` 目录可以运行
> 
> 但是 `C:/Users/某人/测试/jd-shopper/` 运行会报错
>
> 目前的v1.2.1只支持win11版本，如果win10运行可能会有无法预知的错误

### 通过 *源代码* 运行

#### 运行环境

- [Python 3](https://www.python.org/)

#### 第三方库

- [Requests](http://docs.python-requests.org/en/master/)
- [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- [lxml](https://lxml.de)
- [pyyaml](https://pyyaml.org)

V1.2.1以上版本可以自动检查并安装依赖

> 如果自动安装依赖出错，请挑选以下命令手动安装依赖：
> 
> ```sh
> pip install -r requirements.txt
> pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
> python3 -m pip install -r requirements.txt
> pip install lxml pyyaml bs4 requests stora
> ```

### *web*界面 - 使用教程

1. 推荐 **Chrome** 浏览器
2. 到 */TEST/area_id/* 目录下查询你所在地的地区标识ID
3. 如果你的账户有**京豆京券余额**，请到 */Config/config.yaml* 设置密码，或者换个账号运行
4. 命令行运行服务

```shell
python3 runserver.py
```

> **注意**：Windows环境下没有反应的话可以尝试
>
> ```shell
> python runserver.py    # Python环境问题所致
> py runserver.py    # Python环境问题所致
> ```

5. 浏览器打开 http://localhost:12021/

### *命令行* - 使用教程

#### 1. 命令行可自定义各种功能，也许命令行更适合你

#### 2. 网页扫码登录，或者账号密码登录

#### 3. 填写config.yaml配置信息

(1)`eid`和`fp`找个普通商品随便下单,然后抓包就能看到,这两个值可以填固定的
> 随便找一个商品下单，然后进入结算页面，打开浏览器的调试窗口，切换到控制台Tab页，在控制台中输入变量`_JdTdudfp`，即可从输出的Json中获取`eid`和`fp`。  
> 不会的话参考作者3的👉 [使用教程请参看Wiki](https://github.com/tychxn/jd-assistant/wiki/1.-%E4%BA%AC%E4%B8%9C%E6%8A%A2%E8%B4%AD%E5%8A%A9%E6%89%8B%E7%94%A8%E6%B3%95)
>
> *不会的同学也可以打开`TEST`目录下的`get_eid_fp.html`文件，不过有概率失败*

(2)到 `/TEST/area_id/` 目录下查询你所在地的地区标识ID

(3)`sku_id`,`DEFAULT_USER_AGENT`
> `sku_id`已经按照Xbox Series S的填好。
> `cookies_string` 现在已经不需要填写了
> `DEFAULT_USER_AGENT` 可以用默认的。谷歌浏览器也可以浏览器地址栏中输入about:version 查看`USER_AGENT`替换

(4)配置一下时间
> 现在不强制要求同步最新时间了，程序会自动同步京东时间
>
> > 但要是电脑时间快慢了好几个小时，最好还是同步一下吧

以上都是必须的.
> tips：
> 在程序开始运行后，会检测本地时间与京东服务器时间，输出的差值为本地时间-京东服务器时间，即-50为本地时间比京东服务器时间慢50ms。
> 本代码的执行的抢购时间以本地电脑/服务器时间为准

(5)修改抢购件数
> 代码中默认抢购件数为2
> 具体修改为：在config.yaml文件

(6) **特别提示！** *不止一个人卡在这个问题，如果不注意至少花两个小时调试debug*
> 如果你的账户中有可用的京券（注意不是东券）或 在上次购买订单中使用了京豆，
> 那么京东可能会在下单时自动选择京券支付 或 自动勾选京豆支付。
> 此时下单会要求输入六位数字的支付密码。请在config.yaml配置你的支付密码，如 123456 。
>
> 显著特点是添加购物车能成功，但一到订单结算页面就报错，基本就是这个原因！

#### 4.运行main.py

```sh
python3 main.py
```

> **注意**：Windows环境下没有反应可以尝试
>
> ```shell
> python main.py    # Python环境问题所致
> py main.py    # Python环境问题所致
> ```



根据提示选择相应功能即可

#### 5.抢购结果确认

抢购是否成功通常在程序开始的一分钟内可见分晓！  
搜索日志，出现“抢购成功，订单号xxxxx"，代表成功抢到了，务必半小时内支付订单！程序暂时不支持自动停止，需要手动STOP！  
若两分钟还未抢购成功，基本上就是没抢到！程序暂时不支持自动停止，需要手动STOP！

## 自行打包可执行文件
> 本方法依赖 **PyInstaller**，也可采用其他模块进行打包
> 打包入口在runserver.py
1. 修改Config/config.yaml文件
 ```shell
 # 修改GUI模块
 GUI:
    open: true
 #修改Depend模块
Depend:
  open: false
 ```
2. 安装打包依赖
```shell
pip install GUI/pack_requirements.txt
```
3. 使用 PyInstaller 进行打包
```shell
python GUI/packing.py
```
4. 生成可执行文件在 dist/目录中

## 感谢

##### 作者-1 https://github.com/zhou-xiaojun/jd_mask 的开源项目

##### 作者-2 https://github.com/wlwwu/jd_maotai 的开源项目

##### 作者-3 https://github.com/andyzys/jd_seckill 的开源项目

##### 作者-4 https://github.com/tychxn/jd-assistant 的开源项目

##### 作者-5 https://gitee.com/iszhangk/jd_robot 的开源项目



