# python 爬虫

>python 3

- [gitbook---Python3网络爬虫开发实战](https://germey.gitbooks.io/python3webspider/content/)

- 1.请求库
- 2.解析库
- 3.数据库
- 4.存储库
- 5.web 库
- 6.app 爬虫相关的库
- 7.爬虫框架


## 1.请求库安装
- [requests：python http 请求库(阻塞式的)](https://github.com/requests/requests)
  - doc: http://docs.python-requests.org/en/master/


- [selenium：自动化测试工具](https://github.com/SeleniumHQ/selenium/tree/master/py)
  - Home:	http://www.seleniumhq.org
  - Docs:	selenium package API
  - Dev:	https://github.com/SeleniumHQ/Selenium
  - PyPI:	https://pypi.org/project/selenium/

- ChromDriver 安装
>从ChromeDiver对应表中可以推出：Driver为奇数时，对应的Chrome版本为 `偶数~偶数+2`；Driver为偶数时，对应的Chrome版本为 `奇数~奇数+2`；
所以就可以以这种对应关系推断出自己版本对应的Driver。

  - 驱动浏览器完成相应的操作
  - [chromedriver/downloads](https://sites.google.com/a/chromium.org/chromedriver/downloads)
  - [chromedriver 驱动下载地址](http://chromedriver.storage.googleapis.com/index.html)
  - [chrome所有版本驱动](http://npm.taobao.org/mirrors/chromedriver/)
  - 环境变量配置：1.将 chromedriver.exe文件拖到 python 到 Script 目录下，也可以单独将所在路径配置到环境变量
    ```
      当然，也可以将 hromeDriver 配置到$PATH 首先，可以将可执行文件放到某 目录，目录可以
      任意选择，例如将当前可执行文件放在／ sr/local/chromedri ver 录下，接下来可以修改～／ profile 文件，
      相关命令如下
      export PATH=” $PATH:/usr/local/chromedriver"
      保存后执行如下命令：
      source -I. profile
      即可完成环境变量的添加
    ```

- 验证安装： 配置完成后，就可以在命令行下直接执行 chromedriver 命令了：
  ```
    chromedriver
    
    如果出现
    C:\Users\fairy>chromedriver
    Starting ChromeDriver 70.0.3538.97 (d035916fe243477005bc95fe2a5778b8f20b6ae1) on port 9515
    Only local connections are allowed.
  ```

- 随后再在程序中测 Python 代码：
```
from selenium import webdriver
browser = webdriver.Chrome()
```

运行之后 如果弹出一个空 Chrome 浏览器，则证明所有的配置都没有问题，如果没有弹出，    
请检查之前的配置  

如果弹出后闪退，则可能 ChromeDriver 版本和 Chrome 版本不兼容 ，请更换 ChromeDriver    
如果没有问题，接下来就可以利用 Chrome 来做网页抓取了

- 如果驱动火狐浏览器就需要 GeckoDriver 安装
  - github: https://github.com/mozilla/geckodriver
  - download: https://github.com/mozilla/geckodriver/releases
 
- PhantomJS
  - website: http://phantomjs.org/ 
  - doc: http://phantomjs.org/quick-start.html
  - api: http://phantomjs.org/api/
  - download: http://phantomjs.org/download.html 
  - github: https://github.com/ariya/phantomjs/
  - 环境变量配置：1.将 bin 目录中 phantomjs.exe文件拖到 python 到 Script 目录下，也可以单独将bin所在路径配置到环境变量

- [aiohttp: 异步的web服务库](https://github.com/aio-libs/aiohttp)
  - [docs](https://docs.aiohttp.org)
  - 官方还推荐安装如下两个库 个是字符编码检测库 cchardet ，另 加速 DNS 解析库：aiodns
  - `pip3 install cchardet aiodns` 或 `python3 -m pip install cchardet aiodns`

## 2.解析库安装
- [lxml:python 解析库，支持 html 和 xml,支持 xpath 解析方式](https://github.com/lxml/lxml)
  - pip 安装方式： pip3 install lxml
  - wheel 安装方式： 需要先安装 wheel, pip3 install wheel, 下载 .whl 文件，然后 pip3 install lxml-3.8.0-cp36_amd64.whl
  - 验证安装
    - python3
    - >>>import lxml  //如果没有报错，就说明库已经安装好了 

- beautiful soup: html或 xml 解析器
  - docs(中文文档): https://beautifulsoup.readthedocs.io/zh_CN/v4.4.0/
  - 官方网站: http://www.crummy.com/software/BeautifulSoup/
  - 原版文档: http://www.crummy.com/software/BeautifulSoup/bs4/doc/
  - 虽然安装的名是 `BeautifulSoup4` ,但是引入的 `bs4`

- pyquery: 网页解析工具，提供和 jQuery 类似的语法来解析HTML文档，支持css 选择器
  - github: https://github.com/gawel/pyquery
  - docs: https://pyquery.readthedocs.io/en/latest/

- tesserocr :python OCR 识别库，OCR(Optical Character Recognition，光学字符识别)，核心：tesseract,安装之前先安装 tesseract
  - github: https://github.com/sirfz/tesserocr
  - GitHub： https://github.com/tesseract-ocr/tesseract
  - docs: https://github.com/tesseract-ocr/tesseract/wiki
  - tesseract downloads: https://digi.bib.uni-mannheim.de/tesseract/
    - 我下载的 tesseract-ocr-setup-3.05.01.exe ,下载后双击安装
    - 接下来 再安装 tesserocr 可，此时直接使用 ip 安装
      ```pip3 install tesserocr pillow ```

## 数据库安装
- 1.MySQL:
  - download: https://www.mysql.com/downloads/
  - windows-download: https://dev.mysql.com/downloads/installer/
- 2.MongoDB：
- 3.redis：
  - GitHub：https://github.com/antirez/redis
  
  
## 4.存储库

- 1.PyMySQL: 如果想将数据存储到 MySQL， 就需要借助 PyMySQL，
  - GitHub：https://github.com/PyMySQL/PyMySQL
  - dochttps://pymysql.readthedocs.io/en/latest/
  - 验证：import pymysql
    - pymysql.VERSION //如果输出版本，就说明安装成功

- 2.PyMongo:和MongoDB 交互，就需要 PyMongo
  - GitHub： https://github.com/mongodb/mongo-python-driver
  - docs: http://api.mongodb.com/python/

- 3.redis-py: 使用 redis 需要 redis-py 库
  - GitHub：https://github.com/andymccurdy/redis-py
  - docs: https://redis-py.readthedocs.io/en/latest/
  - redisdump: 用于 redis 导入、导出的工具，基于 ruby 实现的，需要先安装 ruby 
    - github: https://github.com/delano/redis-dump
    - docs: http://delanotes.com/redis-dump/
    - ruby-download: http://www.ruby-lang.org/zh_cn/documentation/installation/  
      https://rubyinstaller.org/downloads/
    - 安装后就可以使用 gem 安装，
    - `gem install redis-dump`

## 5.web库安装
- 1.Flask 安装：web 服务程序，主要做一些 API 服务，
  - github: https://github.com/pallets/flask
  - Website: https://www.palletsprojects.com/p/flask/
  - docs: https://palletsprojects.com/p/flask/ 
  
  
- 2.Tornado: 支持异步的 web 框架，使用 非阻塞 I/O流，支持上千万的开放连接，
  - GitHub：https://github.com/tornadoweb/tornado
  - docs: http://www.tornadoweb.org/en/stable/

- 3.django
  - GitHub：https://github.com/django/django
  - windows-install: https://docs.djangoproject.com/zh-hans/2.0/howto/windows/
  - 


## 6.APP 爬取相关库安装
- 1.charles
- 2.mitmproxy
- 3.Appium


## 7.爬虫框架
- [scrapy](https://github.com/scrapy/scrapy)
  - 需要先安装 lxml,pyOpenSSL,Twisted,pyWin32
  - twisted: https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted
    - install: python3 -m pip install Twisted-18.9.0-cp37-cp37m-win_amd64.whl
  - pywin32: https://sourceforge.net/projects/pywin32/files/pywin32/
    - 安装后来找不到模块，去[GitHub](https://github.com/mhammond/pywin32/releases)下载文件有安装的
  - 安装好依赖后 在安装 `python3 -m pip install Scrapy`
- [pyspider](https://github.com/binux/pyspider)
  - 依赖 phantomjs,需要先安装 
  - install: python3 -m pip install pyspider
- [webmagic](https://github.com/code4craft/webmagic)
- [scrapy-redis](https://github.com/rmax/scrapy-redis)
  - install: python3 -m pip install scrapy-redis
- [scrapy-splash](https://github.com/scrapy-plugins/scrapy-splash)
  - install: python3 -m pip install scrapy-splash


## 部署相关的库安装
- 1.Docker 安装
  - website: https://www.docker.com/
  - GitHub：https://github.com/docker
  - 中文社区： http://www.docker.org.cn/
  - 中文教程： http://www.runoob.com/docker/docker-tutorial.html
  - windows download: https://docs.docker.com/docker-for-windows/
- 2.Scrapyd 安装：部署和运行 Scrapy 项目的工具，基本都是使用 Linux 主机
- 3.Scrapyd-Client:
- 4.Scrapyd-API:
- 5.Scrapyrt:
- 6.Gerapy:




## 验证码识别

- [图像验证码识别](https://github.com/Python3WebSpider/CrackImageCode)






## 参考
- [Python3WebSpider](https://github.com/Python3WebSpider)
