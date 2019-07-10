

```python
First, get the html.
由于搜狗搜索引擎，搜索 微信文章，未登录状态仅显示 前10页的内容，需要登录 微信号，才可以看到全部搜索结果。
但是，过于频繁访问，会被搜狗反爬虫 封掉 IP，因此，为避免出现状况，故需要使用 IP代理池，维护一堆有效的IP，以此爬取需要的信息。

第一步目标：通过headers获取微信登录账号的cookies，看到所有搜狗搜索的结果。
```


```python
from urllib.parse import urlencode

import requests
from requests.exceptions import ConnectionError

first_url = 'https://weixin.sogou.com/weixin?'

headers = {
    'Cookies': 'SUV=1562296422075456; SMYUV=1562296422082098; UM_distinctid=16bc01f90309-064cfe2c1c030f-70226752-1fa400-16bc01f9038210; IPLOC=CN4403; SUID=FDEA07743220910A000000005D248315; ABTEST=8|1562673946|v1; SNUID=D6B467482623AB18475EB71B274DC083; weixinIndexVisited=1; sct=6; JSESSIONID=aaaVco0cEzZSJ4gb38rTw; ld=Nyllllllll2NJw50lllllV16k@klllllNlK$@yllllwllllljylll5@@@@@@@@@@; clientId=18668C94D8AF63CE0AAC8100D9676253; pgv_pvi=9504873472; pgv_si=s3158085632; LSTMV=245%2C26; LCLKINT=574; ppinf=5|1562674380|1563883980|dHJ1c3Q6MToxfGNsaWVudGlkOjQ6MjAxN3x1bmlxbmFtZToxODolRTklQjklOEYlRTQlQjglQkV8Y3J0OjEwOjE1NjI2NzQzODB8cmVmbmljazoxODolRTklQjklOEYlRTQlQjglQkV8dXNlcmlkOjQ0Om85dDJsdURxV2VGNjBZREJXa3JsQThLOEEzWGtAd2VpeGluLnNvaHUuY29tfA; pprdig=HVAD9sBmjf4HOQGK573-zr2KG8JrXL1OaREYZP4SocolsFLo0ahDbMKKTd-qa1Mha_ni4XjNauXPMMvSp93DNqV0_Mc2ZChaNXZCCbfw3PO-QxKhPW4OQntjBvCbnq-KLS0I0w47b6qjagZ_N2Sa9IzvmUeT2sefFrgsCujR0gM; sgid=24-35240773-AV0khMyTbVIN0e2asKvmtXM; ppmdig=1562677532000000cc50e64c9e7307154bff7ba0f9e83de6',
    'Host': 'weixin.sogou.com',
    'Upgrade-Insecure-Requests': '1',
    'User-Agent': 'Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:67.0) Gecko/20100101 Firefox/67.0'
}

def get_first_html(url):
    try:
        response = requests.get(url, allow_redirects = False, headers = headers) # 增加 allow_redirects是为了避免302代码执行出现的跳转
        if response.status_code == 200:
            return response.text
        if response.status_code == 302:
            pass
    except ConnectionError:
        return get_first_html(url)

def get_index_page(keyword, page):
    data = {
        'query': keyword,
        'type': 2,
        "page": page
    }
    queries = urlencode(data)
    url = first_url + queries
    html = get_first_html(url)
    print(html)

if __name__ == '__main__':
    get_index_page('natural language processing', 1)
```

    
    <!doctype html>
    <html>
    <head>
        <link rel="shortcut icon" href="//www.sogou.com/images/logo/new/favicon.ico?v=4" type="image/x-icon">
        <link href="//dlweb.sogoucdn.com/logo/images/2018/apple-touch-icon.png" id="apple-touch-icon" rel="apple-touch-icon-precomposed"/>
        <link href="//www.sogou.com/sug/css/m3.min.v.7.css" rel="stylesheet" type="text/css">
        <link href="/new/pc/css/weixin-public-new.min.css?v=20190415" rel="stylesheet" type="text/css">
        
            <link href="/new/pc/css/datepicker.min.css?v=20161107" rel="stylesheet" type="text/css">
        
        <meta http-equiv="X-UA-Compatible" content="IE=Edge">
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
        <meta http-equiv="Access-Control-Allow-Origin" content="*">
        <meta content="width=device-width,initial-scale=1.0" id="vp" name="viewport">
        <title>natural language processing的相关微信公众号文章 – 搜狗微信搜索</title>
        
        <script>
            var sst = {h_s :(new Date()).getTime()};
            var newpage = 1;
            var passportUserId = "";
            var oldQuery = "natural language processing";
            var gbkQuery = "natural+language+processing";
            var uuid = "b09afe47-0e52-4ef1-ac77-cce8e34a62ae";
            var keywords_string = "natural language processing";
            var sab = "0";
            var keywords = oldQuery.split(' ');
            var now = 1562763280642;
            var idc = "sjs";
            var clientIp = "116.7.234.243";
            var isIpad = false;
            //var article_anti_url = "";
        </script>
        <script>
            //以下为动态的全局 js，防止外部网站通过 window.opener.location 篡改我们的页面，以后不要通过 window.location 获取当前地址，只能用 document.location
            
        </script>
        <script src="/js/jquery-1.11.0.min.js" charset="gbk"></script>
        <script src="/new/pc/js/https_util.min.js?v=20180607"></script>
        <script src="/js/lib/juicer-min.js"></script>
        <script src="/new/weixin/js/common.min.js?v=20180607"></script>
        <script src="/new/pc/js/common.min.js?v=20180607"></script>
        
        <script>
            var uigs_para = {
                "uigs_t": "1562763280642",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "b09afe47-0e52-4ef1-ac77-cce8e34a62ae",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "-1",
                "exp_id_list"   : "0_0",
                "wuid"          : "",
                "snuid"         : "F7EE0377030689502D3209C30454E298",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "1"
            };
        </script>
    </head>
    <body>
        
    
    <!--start header-->
    <div class="header-box">
        
        <div class="login-info">
            <a id="top_login" href="javascript:void(0);" uigs="home_login_top">登录</a>
        </div>
    
        <div class="header" id="scroll-header">
            <a title="回到搜狗首页" href="/" name="scroll-nav" class="logo" uigs="home"></a>
            <ul class="searchnav" name="scroll-nav">
                <li><a id="sogou_xinwen" href="http://news.sogou.com/news?ie=utf8&p=40230447&query=natural language processing" onclick="navBar(this,'query=');" uigs="nav_xinwen">新闻</a></li>
                <li><a id="sogou_wangye" href="http://www.sogou.com/web?ie=utf8&query=natural language processing" onclick="navBar(this,'query=');" uigs="nav_wangye">网页</a></li>
                <li class="cur"><a href="javascript:void(0)">微信</a></li>
                <li><a id="sogou_zhihu" href="http://zhihu.sogou.com/zhihu?ie=utf8&p=73351201&query=natural language processing" onclick="navBar(this,'query=')" uigs="nav_zhihu">知乎</a></li>
                <li><a id="sogou_tupian" href="http://pic.sogou.com/pics?ie=utf8&p=40230504&query=natural language processing" onclick="navBar(this,'query=')" uigs="nav_tupian">图片</a></li>
                <li><a id="sogou_shipin" href="https://v.sogou.com/v?ie=utf8&p=40230608&query=natural language processing" onclick="navBar(this,'query=')" uigs="nav_shipin">视频</a></li>
                <li><a id="sogou_mingyi" href="https://www.sogou.com/web?m2web=mingyi.sogou.com&ie=utf8&query=natural language processing" onclick="navBar(this,'query=')" uigs="nav_mingyi">明医</a></li>
                <li><a id="sogou_yingwen" href="http://english.sogou.com/english?b_o_e=1&ie=utf8&query=natural language processing" onclick="navBar(this,'query=')" uigs="nav_yingwen">英文</a></li>
                <li><a id="sogou_wenwen" href="http://wenwen.sogou.com/s/?ch=weixinsearch&w=natural language processing" data-index="http://wenwen.sogou.com/?ch=weixinsearch" onclick="navBar(this,'w=')" uigs="nav_wenwen">问问</a></li>
                <li><a id="sogou_xueshu" href="http://scholar.sogou.com/xueshu?ie=utf-8&query=natural language processing" onclick="navBar(this,'query=')" uigs="nav_xueshu">学术</a></li>
                <li><a id="top_more" href="http://www.sogou.com/docs/more.htm?v=1" target="_blank" uigs="nav_more">更多>></a></li>
            </ul>
            
    
    <form name="searchForm" action="/weixin">
        <div class="querybox">
            <div class="qborder">
                <div class="qborder2">
                    <input type="hidden" name="type" value="2"/>
                    <input type="hidden" name="s_from" value="input"/>
                    <input type="text" class="query" name="query" id="query" ov="natural language processing" value="natural language processing" autocomplete="off"/>
                    
                        <input type="hidden" name="ie" value="utf8"/>
                    
                    <a href="javascript:void(0)" class="qreset2" name="reset" uigs="search_reset"></a>
                </div>
            </div>
            <input type="button" value="搜文章" class="swz" onclick="search(this,2)" uigs="search_article"/>
            <input type="button" value="搜公众号" class="swz2" onclick="search(this,1)" uigs="search_account"/>
            <input type="hidden" name="_sug_" value="n"/>
            <input type="hidden" name="_sug_type_" value=""/>
        </div>
    </form>
            
        </div>
    </div>
    <!--end header-->
        
        <div class="wrapper" id="wrapper">
            <div class="main-left" id="main">
                
    <div class="dy-pop2 dy-pop5 float" id="share_box" style="display: none">
        <a href="javascript:void(0)" class="close" data-except="1" uigs="other_float_share_close"></a>
        <div class="fxico-box">
            <a href="javascript:void(0)" class="sina" data-except="1" uigs="other_float_share_sina"></a>
            <a href="javascript:void(0)" class="renren" target="_blank" data-except="1" uigs="other_float_share_renren"></a>
            <a href="javascript:void(0)" class="douban" target="_blank" data-except="1" uigs="other_float_share_douban"></a>
        </div>
    </div>
    
    
    <div class="dy-pop2 dy-pop5 float" id="erweima_box" style="display: none"></div>
    <script type="text/template" id="erweima_tpl">
        <a href="javascript:void(0)" class="close" data-except="1" uigs="other_float_weixin_close"></a>
        <div class="fxico-box2">微信扫一扫关注<br/><img width="104" height="104" src="${imgsrc}"/></div>
    </script>
                
    
    <script>
        //高级工具参数对象
        var toolParas = {
            tsn : '0',
            ft : '',
            et : '',
            interation : '',
            wxid : '',
            usip : ''
        };
        var from_tool = '0';
    </script>
    <div class="wx-topbox">
        <div class="all-time">
            <div class="all-time-y2 ">
                <div class="all-time-y all-time-y-v1" id="text">
                    以下内容来自微信公众平台<div class="tool" id="tool_show"><a href="javascript:void(0)" uigs="select_show">搜索工具</a></div>
                </div>
                
                    <div class="all-time-y" id="tool">
                        <span class="all-wy-box">
                            <a href="javascript:void(0)" class="btn-time" id="time" data-except="1">全部时间</a>
                            <div class="time-box float" style="width:120px; left:0px; display: none;">
                                <i></i>
                                <a href="javascript:void(0)" class="time-range" data-type="0" uigs="select_time_all">全部时间</a>
                                <a href="javascript:void(0)" class="time-range" data-type="1" uigs="select_time_day">一天内</a>
                                <a href="javascript:void(0)" class="time-range" data-type="2" uigs="select_time_week">一周内</a>
                                <a href="javascript:void(0)" class="time-range" data-type="3" uigs="select_time_month">一月内</a>
                                <a href="javascript:void(0)" class="time-range" data-type="4" uigs="select_time_year">一年内</a>
                                <div class="zdy">
                                    <span>自定义</span>
                                    <input type="text" id="date_start" placeholder="从">
                                    <input type="text" id="date_end" placeholder="至">
                                    <p class="input-box-err" style="display: none;">时间格式错误</p>
                                    <a href="javascript:void(0)" class="enter" id="time_enter" data-except="1" uigs="select_time_zdy">确认</a>
                                </div>
                            </div>
                        </span>
                        <span class="line"></span>
                        <span class="all-wy-box">
                            <a href="javascript:void(0)" class="btn-time" id="type" data-except="1">全部类型</a>
                            <div class="time-box float" style="left: -19px; display: none;">
                                <form action="javascript:void(0)" data-except="1">
                                    <i></i>
                                    
                                    <span><input type="checkbox" class="check" value="458754" id="check_pic" data-except="1"><label for="check_pic" data-except="1">图集</label></span>
                                    
                                    <span><input type="checkbox" class="check" value="458756" id="check_video" data-except="1"><label for="check_video" data-except="1">含视频</label></span>
                                    <a href="javascript:void(0)" class="enter" id="type_enter" data-except="1" uigs="select_type_yes">确认</a>
                                </form>
                            </div>
                        </span>
                        <span class="line"></span>
                        <span class="all-wy-box">
                            <a href="javascript:void(0)" class="btn-time" id="search" data-except="1">账号内搜索</a>
                            <div class="time-box float" style="width:200px; left:-116px; display: none;">
                                <form action="javascript:void(0)">
                                    <i></i>
                                    <span class="input-box">
                                        <input type="text" class="s-sea" placeholder="输入公众号或微信号" data-except="1">
                                        <a href="javascript:void(0)" id="search_enter" data-except="1" uigs="select_search_yes"></a>
                                    </span>
                                    <p class="input-box-err" style="display: none;">没有找到相应的公众号</p>
                                </form>
                            </div>
                        </span>
                        <span class="line"></span>
                        <div class="tool" id="tool_hide" style="display: none"><a href="javascript:void(0)" uigs="select_hide">收起工具</a></div>
                        <div class="tool tool-v1" id="tool_clear" style="display: none"><a href="javascript:void(0)" uigs="select_clear">取消筛选</a></div>
                    </div>
                
            </div>
        </div>
    </div>
    
        <script src="/new/pc/js/datepicker.min.js?v=20161107"></script>
        <script src="/new/pc/js/tool.min.js?v=20180509"></script>
    
    
    <div class="news-box">
        
    <ul class="news-list">
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-3d17fdf66ca8f27d91f31f908a964648">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9DjyOYOQT8fzHWfgJRjTBpjztgPfe6jUBqpQbMCFWgj8V896vjobBMaC-IZx_lf9o4fS7uwLUIWIZOvk-0uxCwurHSCrKsE18G4Hf1jDvVs28EakT01vJVVPermb5A7oaAdObG2WL30vTMGH9ZpuOQjz7DoKHq2Me_Vqx8pQLCw1Ae0f8bRARvQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/hflWRBRSEZ5wBH9lFgN1Fib7SyBE8tZV90Inbr2SPo01AGtNicn2sX9OtsmOJUZ5xRt5q5wMPyFz5IEPoMbxnZFA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9DjyOYOQT8fzHWfgJRjTBpjztgPfe6jUBqpQbMCFWgj8V896vjobBMaC-IZx_lf9o4fS7uwLUIWIZOvk-0uxCwurHSCrKsE18G4Hf1jDvVs28EakT01vJVVPermb5A7oaAdObG2WL30vTMGH9ZpuOQjz7DoKHq2Me_Vqx8pQLCw1Ae0f8bRARvQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOk8ODWwYJcpjTOt3iiFrFTLDRu*PJHC2jJl7BgsyR5fCey6-nRyGWpOD-dTEEwIv2j7DVDeGWq9McuJ9jbcdYVxEwIHoMgDnSNu8ma25UkbWT-bGmBMrdE7DpEerdYYpXXmMh9eKOVon5LbA6172TmZmXZ6GRLYnX75ftaP41Z60=">587 页《<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》最新版上线!附pdf 下载</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">重磅干货,第一时间送达乔治亚理工大学的 Jacob Eisenstein 教授开放了自然<em><!--red_beg-->语言<!--red_end--></em>处理领域的最新教材《<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>...</p>
    <div class="s-p" t="1550278226">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFt_T7okp5uImZhEeT1LrE7a0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzqRxoPHlgMl9eXUzitMHif9liHwi2ND9ulvvLPLYt6T9Cdy0QZmSbvuThFHsL7N2JMrFOCgIhZxraTn35FuupGn9DHsPQ_7TH0WiVX60nKNoHGQI9KgjtQG4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5c2psn761MPiasicWs6DrdvIb8oQxN4ej69OLjNyzN2Z0g/0" data-isV="0" uigs="article_account_0">AI有道</a><span class="s2"><script>document.write(timeConvert('1550278226'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-4fa813da5ef28e8ae1659bbf898ed74f">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9TNNBDmpESWS65CQn50dLbYJFf7RqOmp2AJJMc0nOHUMoLjRBHAtbNfQLgRHeCQaHe7uX2SlPcDP64LpFUMo0hsSm8XOehUxUZpfx4MFdgT7-QL4l02lO6PmpVQZ7CYfkLBTlNpeVvsoPp41K8AoEhCMiBT7Xbd6BhtszsEUBYB31AfaFW2DefQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/D2B7FzRKlwicib6kNPvIZRoUf0oSiab2hzib45u3Fgjdibbox7qWh2ceR4HSZ9MOftytkZKvfWHeX87fLrYODSqGImw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9TNNBDmpESWS65CQn50dLbYJFf7RqOmp2AJJMc0nOHUMoLjRBHAtbNfQLgRHeCQaHe7uX2SlPcDP64LpFUMo0hsSm8XOehUxUZpfx4MFdgT7-QL4l02lO6PmpVQZ7CYfkLBTlNpeVvsoPp41K8AoEhCMiBT7Xbd6BhtszsEUBYB31AfaFW2DefQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOXVdDAcpkmC0Q*vgkVKCwe8xVJ4mPDz3GgQ3KD-O2Jn8D1TSRuuR76fZBx-N2YEvivwlHf5loZLtWeizQ4Vqfw*Jp93HYynHzU4IWkBJ-DN-BsaZYLUgY*VLoMxMEdnZFps91JCoP7iqBA7YhSfCx-HXp0pbKv-k05J8Vdj-lzM0=">讲座推荐| <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> for Assessing Health News</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1"><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> for Assessing Health News Quality (大数据时代情报学与情报工作系列讲座)主讲人Bei Yu is the ...</p>
    <div class="s-p" t="1531317420">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt9hlxunDPTkDHhXqV5n8vpk" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzua0rIClBb94AYLLfy0S_EftKRxCiEIoRUPQNB7SX9iSmMHUyDZQ7Jm8s8L6wE9ZClx3-yMEjFER9yIYMsZS7-rX0OHVpUj3yYf4ceQI0nuyEeBz2uVim7qUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7lWbNGubPg5K5BWQOibpAo9vQh4JB5UqVqaCSHmafeQVw/0" data-isV="1" uigs="article_account_1">川大公管院</a><span class="s2"><script>document.write(timeConvert('1531317420'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-a174a8c3de51554120e6b6cc57810aaf">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9DEDjs5snc_4nMmXJv7D8-0IKNR5GCe96X2FD4BaUN__8RkhKxdiaPvdnOElsUa5J6W0x-ArGlGAtZNfwvwMkYoGdodImvih7mM6aSgps7mU21t1No2n0wtWrwfoRyZ7sTB8sHi9XI868P5R2Zk16vLOJQaDrM7NAD6ciJhcBLexCy6umSSPEsg..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/M47bfSjUwgQr3TusIq60g4nghsj40AiaV838cvFRtHjVMH13ML4NwNSoefmVSzoHTD4062dgg3PJGIqBxBy0QIg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9DEDjs5snc_4nMmXJv7D8-0IKNR5GCe96X2FD4BaUN__8RkhKxdiaPvdnOElsUa5J6W0x-ArGlGAtZNfwvwMkYoGdodImvih7mM6aSgps7mU21t1No2n0wtWrwfoRyZ7sTB8sHi9XI868P5R2Zk16vLOJQaDrM7NAD6ciJhcBLexCy6umSSPEsg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOP618VN8DR1IojS*gCijZlEWDU32Cy2Djui4376z9opV4ke46r6YDjW0-isyUOr08aSRW95W6sh3N-7s4qnS3Hu-JiNBd9rRuHFUKO08VNvdhdznMlQtdR-FQuqISK7oPXmqENJUKNIHvN4YYCwO1OhrJDQi3uvNm6lLEpjc*o6Y="><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> in Action 电子书推荐</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">书籍描述:自然<em><!--red_beg-->语言<!--red_end--></em>处理在实际中是您创建机器的指南,这些机器使用Python的强大功能理解人类<em><!--red_beg-->语言<!--red_end--></em>,其软件包生态系统专用于NLP...</p>
    <div class="s-p" t="1561527833">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFt8yFJv03dCkOU4UQNMITImg" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzRL5SnwLbRrTasLAfZM2OTwfzLp4VgHoPxT7i5R5sCY5zpAxh2ssDJRfKZrbl4KTPQiOQOnf2oGUwqs4UFsTiHV6Sp-CvWUJqFIGsKeHPItAof9HtneyUxeO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6kmDq8XThnwTWQCwxMtVsu4KF4Ybnia8l1HzAtOeuoiaqQ/0" data-isV="0" uigs="article_account_2">IIBooks</a><span class="s2"><script>document.write(timeConvert('1561527833'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-f3b094a85a5bd9170aa5b015ffd68429">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9zPYr8KIK5LXzwn0ZAIELCihsgHjHGMSKPIGvToti5uIX7pCaq8TYCPe3LEPaT7ckUmvgkcqmiutRxGaOlMoyoyrFRoJZ13fPcf_cALGfoHyRTVTyma2om3jk5NLSEFGmdBGcVucUHCpOCGV65yLaLgzVf_4y5GAPAcInU7HetSmjotuuiAmOIg..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/bicdMLzImlibQPcOKDCKpBzm9LQXu46ibia7bHLcRNtYsBeOLzUPn5CcicUjJqvkYfoUibFMNiaQuiaP7BZVHxLPRtngSQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9zPYr8KIK5LXzwn0ZAIELCihsgHjHGMSKPIGvToti5uIX7pCaq8TYCPe3LEPaT7ckUmvgkcqmiutRxGaOlMoyoyrFRoJZ13fPcf_cALGfoHyRTVTyma2om3jk5NLSEFGmdBGcVucUHCpOCGV65yLaLgzVf_4y5GAPAcInU7HetSmjotuuiAmOIg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOPZh*Bau9AuPYj6OPFOQcFhqnqi-yLYv*bRjxoQ35in-1GaDbeWD01Of7BdM9MtX85qsqOqPOkt3W81*nz2Fl8UKREh8AGz3aEpWxylLZbQMWlk7nBoIxESKcTFUBMQgIxJavvf*tmwG1dJ9B9eMUDt9T3iI1zTKFPS6WVWQnEoE=">自然<em><!--red_beg-->语言<!--red_end--></em>处理背后的数据科学</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">本文为 AI 研习社编译的技术博客,原标题 :The Data Science Behind <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>作者 | John Thuma翻译 | luyao777 ...</p>
    <div class="s-p" t="1555638590">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFt2sN1DOMaQ5h4Nc4puH3eM0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdz_QngJduzjezLTNLPbDlzszIlNbrRBgc4P8styoR82iqpD0Tb2rFwkgEdLmw8MLI9ndyMbWRw5UlOWWX-l-jGdzkMR7XqxJXfZnAhkn7zZMFhNMHFyCpqWGRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6C2orKhu8vxM7mAt3ibIU19RbSh5BWZh6icOqLysHWWHPQ/0" data-isV="1" uigs="article_account_3">AI研习社</a><span class="s2"><script>document.write(timeConvert('1555638590'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-e1cc36b120e1712ca5c8230360440baf">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9kalZz9BXgZ1Hfa6cU8kU0AItBm2F8JWSXbU38F6UjgRHK_wHM9u-2RIWCIpGhPSM0Dor0BIxfgGSYvkOsUnVnyoDJZ25VHD5yz6u4V3Ox_IbO2iKnync9ay7yLaBKB_uN5orzl61231Lwk2ZEhLbPKdc8NdV007zJ2Qk23N9dZcGX_iHL9MadA..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_png/G8hFes7ezFjuvEPfXMZMicZnmhjLIxZWZGjbUodD7DQ3Fyx9oia14ll9PmRsFiblsUC81DNXx0a8RT9bSGIS5CCibQ/0?wx_fmt=png" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9kalZz9BXgZ1Hfa6cU8kU0AItBm2F8JWSXbU38F6UjgRHK_wHM9u-2RIWCIpGhPSM0Dor0BIxfgGSYvkOsUnVnyoDJZ25VHD5yz6u4V3Ox_IbO2iKnync9ay7yLaBKB_uN5orzl61231Lwk2ZEhLbPKdc8NdV007zJ2Qk23N9dZcGX_iHL9MadA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOrOhMKHCQqwHJM65cCvaSNC2HtRutbOc8McuHGpnzmYZ2*E0ijbECbDIT2OP4FW9CjBkGt258hl5nFsXxnqXHguUhEO02gmO2Z28nyt0PZYBuA-0ENt*oNBEbtZMrX-YKUZ9i6dpyboZFuPsYyCWs7IJhpv8f2qI*fLwJ5-k7lCQ=">Why is <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> important in our society?</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">computers and human (<em><!--red_beg-->natural<!--red_end--></em>) languages, and a machine's ability to understand, or mimic the understanding of human <em><!--red_beg-->language<!--red_end--></em>. ...</p>
    <div class="s-p" t="1557201599">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt6IKtzX4AVlHQzPbD4P-RhE" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzfyCqnhjDugNa9w_Kemup6h2ZcrrQGagWV4Rfmh7kw80o64QQOo5DCFyWbe9MkzUmhW3w3qjU9yWWiPi6N6VwKpYuaV_mJqycNaQAPxP9jmC_MwVcPcqBeGRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6WIeTR7X6uHs5MT94OnGOFibY8VgjGLDmczVMT6up6Dgg/0" data-isV="0" uigs="article_account_4">南风自来</a><span class="s2"><script>document.write(timeConvert('1557201599'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-5f0aca2a23c4c31de08a5098d8f14a17">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU619-BlllbYaBWMyw7PZmhRGnMSe-bwvcqNdW1ZLBQ4LR0gefGiFiTSqjujZX09rXi6ySffFvHSNzOHop4heDkFCtLoMsaM56pMrju-tPGzO6DVblZ9ZhKn141Cy6umSSPEsg..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AefvpgiaIPw2Kx246g2YibLZ4uoW8yDFLJpuMtu9uaibbtmH1MAPuI8rarByL9STZySy1PvhrrMlauibSoxmEqrTWw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU619-BlllbYaBWMyw7PZmhRGnMSe-bwvcqNdW1ZLBQ4LR0gefGiFiTSqjujZX09rXi6ySffFvHSNzOHop4heDkFCtLoMsaM56pMrju-tPGzO6DVblZ9ZhKn141Cy6umSSPEsg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOfx8Jfwfb0qSMYPxNYhbrgYI*PUB30WSAbGgkKYoS2Vi4bDKyz8Gk5uHgs0r-PktrDEO-4HC1BAk00lDbnP-JWL4hhnh3mMJ*ecjio74uTIhxFjqxuYpcfXL5ZojjP144B4pyH9-I0ncFqnBD5NMvtuew54RhY-HO3Y*-pVPhh0A=">清华刘洋与邓力合著338页新书《Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">【导读】邓力博士及刘洋博士等人合著的 Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> 一书系统介绍深度学习在 NLP 常见问题中的...</p>
    <div class="s-p" t="1541507755">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt76uwDKxyiHVKwWo3xeOGlQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzOmfPGPvs25f63z-PZUbG8HxQJWHLEey2lB_Az_B87nOJKBnIhqiDW7MGTbU99d_IxbqfApI7PH6BhddYaTtWZwzdZ5v7amqWKr_diTrKALBnFZk4-e12zOO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7iathEPUfgnAWr4Hml9INphvANAFNW2LkrRd5RxBqiauzA/0" data-isV="0" uigs="article_account_5">专知</a><span class="s2"><script>document.write(timeConvert('1541507755'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-9d168a341b1552b0c00c63561e516344">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9VNqD2-xO98_Qi9Huq1nNLVAI0Jfbx70aJEWa3xZrb9Zyv0xNEXfkEsn-1TVB7EnuMRIPLVvQ6lx57g6WX3xSG4MxpDd6ZCPGmWPUx3IAHDsryiAcRNV57ViAfvZwwEBHAL5XfKBou5DU0IOauQi4FKzdQzZJyYbSSLwNfSzNT3ICn9lOoZLP2Q..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/ptp8P184xjxrUHD380RlfbSOVL2BmEsHaHOXgfvsfeFbyFogDTzuo6ia1jfOOU0kIc5UIN9dmGPBXOmp6WTIVhg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9VNqD2-xO98_Qi9Huq1nNLVAI0Jfbx70aJEWa3xZrb9Zyv0xNEXfkEsn-1TVB7EnuMRIPLVvQ6lx57g6WX3xSG4MxpDd6ZCPGmWPUx3IAHDsryiAcRNV57ViAfvZwwEBHAL5XfKBou5DU0IOauQi4FKzdQzZJyYbSSLwNfSzNT3ICn9lOoZLP2Q..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOwsgaioyf2xviptmdbrxOYgflK6ASaQ1YDQdWZwOwXtG05rUW1OXP51U1WfZLXLk-yPW0GOLsEM16ftECA6Vsz6GYJlvYocxpeY0Yxr7qLNCQJ2md*WmWxliwgee04kno8r9yDipgG4xRjPUxMAxqzWrg2IABcG20mNbfslqMssc=">自然<em><!--red_beg-->语言<!--red_end--></em>处理中注意力机制综述</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">with Visual Attention. Kelvin Xu et al. JMLR, 2015.[13] Ask me anything: Dynamic memory networks for <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>. ...</p>
    <div class="s-p" t="1548328187">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFtyJmSw80AxC5wFWs2Vh-bt8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzK9BoU_6AVP5wHDwcXfcG0udRNNDR8KJVicr8My51Y5hq2d5SeTSxuBz0rBUPSSKqPAFeJyhQWwE2_yFnqlMcIlqapSf-c2guT5QpcbZALuSP4jyn4cKDmeO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM40UKJXCvqrtjIdiaHucmGGe4RBstYzHWS5njG8WaONflA/0" data-isV="1" uigs="article_account_6">人工智能头条</a><span class="s2"><script>document.write(timeConvert('1548328187'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-645e1b31e318db24bd675f5fbf1f6ac2">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtHxZq_Ef3PYwGJM4K9c25ifU4bRAscvpHFCNJ2FQySQsJWy40WTZr5PHo41J49-3KBKaOHb6InzXesTHE97uLmLwEkb74AubMg1ZM6AezbnImUe1qNJF8dHvzHZXxeLdyg..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/pmcpibroMBaIhkHIznEbJgVqrWicG5KnAsS0OIgEyFGSicsa1ic8TWgZ0iaibYicpxMYOtSuzLlKicBVwn0ywAbJOdlE9A/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtHxZq_Ef3PYwGJM4K9c25ifU4bRAscvpHFCNJ2FQySQsJWy40WTZr5PHo41J49-3KBKaOHb6InzXesTHE97uLmLwEkb74AubMg1ZM6AezbnImUe1qNJF8dHvzHZXxeLdyg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOe4CBhTNsLF9L2spwecpO2r*BuHK3NkIyiuqEIV63N7aqj0dSsBBgzi9a25xQWs6sKqrQpdReNZn5-x0rhH72cLjRuUkMSsb3bWYGpxJxwPo54EUb9hzIZFy-V6hW*0ie1vqoYS8cuZuXCQyR124LAigqn5NZCKGxzw27zUE22yk=">清华刘洋与邓力合著338页新书《Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》发布</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">1. 导读Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>是邓力博士及刘洋博士等人合著,文章各章内容是一线青年学者对此方面研究最...</p>
    <div class="s-p" t="1541606416">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt7lBT9vr2q6cqd34liXTzPY" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzn1Rs4xw59cha2vK8ZaLsXteyUUjQYI8Wo1MFb2o67h90tCFXVs1SvgrdLij2CvFYOhwcqnivGMEhOYT5I_9gGjErV1O36q0InbV6E7JyODIvSYXo-ty_vW4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM49ghiaRuhZbiccUprgby7F1ypb9Agm3QaTIic17vAxvx2dQ/0" data-isV="0" uigs="article_account_7">机器学习算法与自然语言处理</a><span class="s2"><script>document.write(timeConvert('1541606416'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-e6bfe885c405987c5e1b670d2f20e3ba">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9FsjMGgtebOfoZzxmCxE7xZy0CZsCf9XjC1LIzDhMJT8sH3Lu--mKgVA7Gp9gv1yxtTMZrsPNWFdToI4b3-E5DQWidDE4-Iv9paJI4MJCtVbjxmqiZrBIJdGcfgXaTdBDCX8yHsJVm5X9OC9Lu8DlDO4qhTFMDBzeKtOJcHNKbbX2CsG6-xMgzQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/KdayOo3PqHBVSZL6Rw2HMpLnqwp9ZTlYwywG1LqyOL9GBmDLcoBPKpoXbBLBtlw4eibmA7hcO9xPHltibyrEb22g/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9FsjMGgtebOfoZzxmCxE7xZy0CZsCf9XjC1LIzDhMJT8sH3Lu--mKgVA7Gp9gv1yxtTMZrsPNWFdToI4b3-E5DQWidDE4-Iv9paJI4MJCtVbjxmqiZrBIJdGcfgXaTdBDCX8yHsJVm5X9OC9Lu8DlDO4qhTFMDBzeKtOJcHNKbbX2CsG6-xMgzQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO1XW5O5ioVMBQ7wVa9TvSnjANpp9Wjw145*ezfcY87gBCAtRzC3J--bOToNT31lcXj8V15zSBVX3QFFa1n*nxyaoyK1iwvxP4sCZIsZYm4RaVulXmpL1qLJmm3BJ5oGCWToG8E7Gkp2L-Bi*bmePOCBVqaVWxDYYy2seFkibb2l0=">338页新书《Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">由邓力博士及刘洋博士等人合著,系统介绍深度学习在 NLP 常见问题中的应用,是当前此方面研究最新、最全面的综述. 同时还对 ...</p>
    <div class="s-p" t="1541520050">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFt7riLABrVqn6xhbkX3pqx3o" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzORHDds6diVIMhyg4Y9A9DHE_yksEgKAJmluIaGYOjEJbU-f9qBLV7uVD-U15uPBH8i0RtWSxUb0xC0ixVk8yB43tBGV6X_LcIVV2SVSBejr_EeNLpTjNKG4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7N4RJ1VQHdfGXibAMNg7xIMMMfFxpt9t6RxECCQeq6Csw/0" data-isV="0" uigs="article_account_8">机器学习算法与Python学习</a><span class="s2"><script>document.write(timeConvert('1541520050'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-3a476b66b298a4dbd9ddc1c42e30b678">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtCgRxcebvIOCCy1QmmO7E7Y5UQQ01FsjLkdYOseyWRxeS6vVGWoj8iKpaiOwPmIQf_Wimz_XMMFhBpidLdqVq1VJLBuaKo0T5nRfBy6bMF8g8xPOiqbApMte0WC6Sbi7DA..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/lFAia5dnhjrX9xrpHrtlSKLv5I2yZgd13YZAiaeribiaVWyoRA6S4UARY04uMX97wAmdnjdSqnCmQE21uxmByrFIicg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWJ0pBvhhKvBuyZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtCgRxcebvIOCCy1QmmO7E7Y5UQQ01FsjLkdYOseyWRxeS6vVGWoj8iKpaiOwPmIQf_Wimz_XMMFhBpidLdqVq1VJLBuaKo0T5nRfBy6bMF8g8xPOiqbApMte0WC6Sbi7DA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763280&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOe4CBhTNsLF9L2spwecpO2pnX2ByYM8gJpLwViJ4mDy8OTHJqvfTg7PT2rtMVCUQ8XKmyBSOWdcGTG6ZjquJUTYdshz6xdGJOuiclDuHWhxRejtfUs0MGzBXLJEayZYW0RtRlYbLZpDv81NL7gPjC8BWG8BoYljO9XA7nL3UqZxM=">一起走进自然<em><!--red_beg-->语言<!--red_end--></em>处理的世界</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">重磅干货,第一时间送达自然<em><!--red_beg-->语言<!--red_end--></em>处理简介自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,简称NLP)就是用计算机来处理、理解以及...</p>
    <div class="s-p" t="1552435224">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt7lBT9vr2q6cqd34liXTzPY" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdzn1Rs4xw59cha2vK8ZaLsXteyUUjQYI8Wo1MFb2o67h90tCFXVs1SvgrdLij2CvFYOhwcqnivGMEhOYT5I_9gGjErV1O36q0InbV6E7JyODIvSYXo-ty_vW4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM49ghiaRuhZbiccUprgby7F1ypb9Agm3QaTIic17vAxvx2dQ/0" data-isV="0" uigs="article_account_9">机器学习算法与自然语言处理</a><span class="s2"><script>document.write(timeConvert('1552435224'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	<span>1</span><a id="sogou_page_2" href="?query=natural+language+processing&type=2&page=2&ie=utf8" uigs="page_2">2</a><a id="sogou_page_3" href="?query=natural+language+processing&type=2&page=3&ie=utf8" uigs="page_3">3</a><a id="sogou_page_4" href="?query=natural+language+processing&type=2&page=4&ie=utf8" uigs="page_4">4</a><a id="sogou_page_5" href="?query=natural+language+processing&type=2&page=5&ie=utf8" uigs="page_5">5</a><a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=2&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约398条结果<!--resultbarnum:398--></div>
    </div>
        
    </div>
    
    
            </div>
            
                <div class="snb-right" id="right">
                    
        <div id="account" class="aside" style="display: none">
            <p class="tit-pub">相关公众号<a target="_blank" href="/weixin?type=1&ie=utf8&query=natural+language+processing" uigs="right0_more">更多</a></p>
            <div class="gzh-list" style="display: none"></div>
            
    		<!-- a -->
    		<div class="gzh-box">
    <div class="img-box2">
    <a target="_blank" uigs="right0_image_10" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdz_7HLqMzjNmVEiwuoXL0lWRXc8Pg5Cmax8hzKSfOHVuItgZMlOn5trXl2xGZue0t-OmMdqyI14Qxl0aEHSRkBhq5KOE-QWHg3iLstDTKCysqNOx-1BEg0l2RTpLLTNgHY&amp;type=2&amp;query=natural language processing"><img height="58" width="58" src="https://img04.sogoucdn.com/app/a/100520090/oIWsFt6H0vSmd7OiiNt8fAQlDxgg" onerror="this.src=&quot;//weixin.sogou.com/wechat/images/account/def56-56.png&quot;;this.onerror=null;"></a>
    </div>
    <div class="txt-box2">
    <p class="gzh-name">
    <a target="_blank" uigs="right0_name_10" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqPHD85P0_c68dvUefuQ9ptgwvDqyjOWdz_7HLqMzjNmVEiwuoXL0lWRXc8Pg5Cmax8hzKSfOHVuItgZMlOn5trXl2xGZue0t-OmMdqyI14Qxl0aEHSRkBhq5KOE-QWHg3iLstDTKCysqNOx-1BEg0l2RTpLLTNgHY&amp;type=2&amp;query=natural language processing"><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em></a>
    </p>
    <p class="gzh-num">微信号：<label name="em_weixinhao">gh_5ec5c77e7f85</label>
    </p>
    </div>
    <dl style="display: none">
    <dt>功能介绍：</dt>
    <dd>Computational Linguistics; Knowledge Graph; Machine Translation; Representation Learning; Social Media; Named Entity; QA</dd>
    </dl>
    </div>
    
    		<!-- z -->
    	
        </div>
        <script>
            if(uigs_para && 1){
                var right = "";
                for(var i = 0; i < 1; i++){
                    right = right + "-right0_" + i;
                }
                uigs_para.right = right.substring(1);//右侧相关公众号展现的标记
            }
        </script>
    
    
    <div id="hotword" class="aside" style="display: none">
        <p class="tit-pub">搜索热词<span class="hot">热度</span></p>
        <ol class="hot-news"></ol>
    </div>
    <script type="text/template" id="hotword_tpl">
        {@if hotwordList}
            {@each hotwordList as wordItem, index}
                {@if wordItem.word}
                    <li>
                        <i class="{@if index == 0}hot-one{@else if index == 1}hot-two{@else if index == 2}hot-three{@/if}">${index|indexPlus}</i>
                        <a target="_blank" id="sogou_wx_hotword_${index}" href="${wordItem.word|buildQueryLink}" uigs="right1_${index|indexPlus}">${wordItem.word|unescapeWord}</a>
                        <span class="lan-line"><span style="width:${index|getRange,7}"></span></span>
                    </li>
                {@/if}
            {@/each}
        {@/if}
    </script>
    
    <script src="/new/pc/js/right.min.js?v=20170315"></script>
    
                </div>
            
        </div>
        <div class="back-top" style="display: none;"><a href="javascript:void(0);" uigs="other_float_back_top"></a></div>
        
        <div class="bottom-form">
            
    
    <form name="searchForm" action="/weixin">
        <div class="querybox">
            <div class="qborder">
                <div class="qborder2">
                    <input type="hidden" name="type" value="2"/>
                    <input type="hidden" name="s_from" value="input"/>
                    <input type="text" class="query" name="query" id="query" ov="natural language processing" value="natural language processing" autocomplete="off"/>
                    
                        <input type="hidden" name="ie" value="utf8"/>
                    
                    <a href="javascript:void(0)" class="qreset2" name="reset" uigs="search_reset"></a>
                </div>
            </div>
            <input type="button" value="搜文章" class="swz" onclick="search(this,2)" uigs="search_article"/>
            <input type="button" value="搜公众号" class="swz2" onclick="search(this,1)" uigs="search_account"/>
            <input type="hidden" name="_sug_" value="n"/>
            <input type="hidden" name="_sug_type_" value=""/>
        </div>
    </form>
        </div>
    
    <div class="footer-box" id="s_footer">
        <div class="footer">
            <a id="sogou_webhelp" href="http://help.sogou.com/" target="_blank" uigs="bottom_ssbz">搜索帮助</a>&nbsp;<a href="http://fankui.help.sogou.com/index.php/web/web/index/type/4" target="_blank" uigs="bottom_yjfk">意见反馈及投诉</a>&nbsp;<script src="/websearch/wexinurlenc_sogou_profile.jsp"></script>&copy;&nbsp;2019&nbsp;SOGOU.COM&nbsp;&nbsp;&nbsp;&nbsp;<a href="http://www.sogou.com/docs/terms.htm" target="_blank" uigs="bottom_mzsm">免责声明</a>&nbsp;<a href="http://corp.sogou.com/private.html" target="_blank" uigs="bottom_yszc">隐私政策</a>
        </div>
    </div>
        
            <script src="/new/pc/js/article.min.js?v=20161212"></script>
        
        <script>
            var WX_SUGG_PAGE_FROM="pcArtSearch";
            
            var SugPara = {
                "bigsize":true,
                "enableSug":true,
                "sugType":"wxart",
                "domain":"w.sugg.sogou.com",
                "productId":"web",
                "sugFormName":"sf",
                "submitId":"stb",
                "suggestRid":"01015002",
                "normalRid":"01019900",
                "oms":1,
                "nofixwidth":1,
                "useParent":1
            };
            uigs_para.exp_id = "null_0-null_1-null_2-null_3-null_4-null_5-null_6-null_7-null_8-null_9-";
            uigs_para.exp_id = uigs_para.exp_id.substring(0, uigs_para.exp_id.length - 1);
        </script>
        <script src="/new/weixin/js/uigs.min.js?v=20180607"></script>
        <script src="/new/pc/js/log.min.js?v=20170321"></script>
        <script src="/new/pc/js/event.min.js?v=20190329"></script>
        <script src="/new/pc/js/search.min.js?v=20161107"></script>
        <script src="/new/pc/js/suggestion.min.js?v=20180607"></script>
        <script src="/new/weixin/js/form.min.js?v=20170101"></script>
        
    
    <script>
        (function(){$("a").on("mousedown click contextmenu",function(){var b=Math.floor(100*Math.random())+1,a=this.href.indexOf("url="),c=this.href.indexOf("&k=");-1!==a&&-1===c&&(a=this.href.substr(a+4+parseInt("26")+b,1),this.href+="&k="+b+"&h="+a)})})();
    </script>
    
    </body>
    </html>
    <!--1562763280642-->
    <!--zly--><!--weixin-->
    
    
