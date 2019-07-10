

```python
第二步，传入 keyword： natural language processing，实现翻页操作，得到所有搜索结果界面。
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

keyword = 'natural language processing'

def get_first_html(url):
    try:
        response = requests.get(url, allow_redirects = False, headers = headers) # 增加 allow_redirects是为了避免302代码执行出现的跳转
        if response.status_code == 200:
            return response.text
        if response.status_code == 302:
            print('出现了错误：302')
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
    return html # 修改部分点

def main():
    for page in range(1, 41):
        html = get_index_page(keyword, page)
        print(html)

if __name__ == '__main__':
    main()
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
            var uuid = "c8dba2c1-c193-45b0-ab7e-55498e96180f";
            var keywords_string = "natural language processing";
            var sab = "0";
            var keywords = oldQuery.split(' ');
            var now = 1562763692822;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763692822",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "c8dba2c1-c193-45b0-ab7e-55498e96180f",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "-1",
                "exp_id_list"   : "0_0",
                "wuid"          : "",
                "snuid"         : "5A5AB7DBAFB53DE3F668F794B08667B6",
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9DjyOYOQT8fzHWfgJRjTBpjztgPfe6jUBqpQbMCFWgj8V896vjobBMaC-IZx_lf9o4fS7uwLUIWIZOvk-0uxCwiwJbhwehAzDlkyVjCRnGO2FtdbviYpaJkcisspV5CDG5SsgkpnLZjg62oS3jZETBoS7S3Tity3lhbyb0q4wWp5j3x9Nw6p-Fg..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/hflWRBRSEZ5wBH9lFgN1Fib7SyBE8tZV90Inbr2SPo01AGtNicn2sX9OtsmOJUZ5xRt5q5wMPyFz5IEPoMbxnZFA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9DjyOYOQT8fzHWfgJRjTBpjztgPfe6jUBqpQbMCFWgj8V896vjobBMaC-IZx_lf9o4fS7uwLUIWIZOvk-0uxCwiwJbhwehAzDlkyVjCRnGO2FtdbviYpaJkcisspV5CDG5SsgkpnLZjg62oS3jZETBoS7S3Tity3lhbyb0q4wWp5j3x9Nw6p-Fg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOk8ODWwYJcpjTOt3iiFrFTLDRu*PJHC2jJl7BgsyR5fCey6-nRyGWpOD-dTEEwIv2j7DVDeGWq9McuJ9jbcdYVxEwIHoMgDnSNu8ma25UkbWT-bGmBMrdE7DpEerdYYpXKEdfiDG10RFRP3hEh0styVimY6Qow4nM73SXT60Svz8=">587 页《<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》最新版上线!附pdf 下载</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">重磅干货,第一时间送达乔治亚理工大学的 Jacob Eisenstein 教授开放了自然<em><!--red_beg-->语言<!--red_end--></em>处理领域的最新教材《<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>...</p>
    <div class="s-p" t="1550278226">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFt_T7okp5uImZhEeT1LrE7a0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzqRxoPHlgMl9eXUzitMHif9liHwi2ND9ulvvLPLYt6T9Cdy0QZmSbvuThFHsL7N2JMrFOCgIhZxraTn35FuupGnZTfv-kPsmcu7kLgLPyFDj60ZESXNe8C6UiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5c2psn761MPiasicWs6DrdvIb8oQxN4ej69OLjNyzN2Z0g/0" data-isV="0" uigs="article_account_0">AI有道</a><span class="s2"><script>document.write(timeConvert('1550278226'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9TNNBDmpESWS65CQn50dLbYJFf7RqOmp2AJJMc0nOHUMoLjRBHAtbNfQLgRHeCQaHe7uX2SlPcDP64LpFUMo0hijLDviShPXuOOnUouom-0tl2yzKWaDpi9RNAM1J9IH5F-qU3j7l4ZN5DpiSerc3RnMTd_PijDMcDCNkil8wUBcY-UZGbO56rA..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/D2B7FzRKlwicib6kNPvIZRoUf0oSiab2hzib45u3Fgjdibbox7qWh2ceR4HSZ9MOftytkZKvfWHeX87fLrYODSqGImw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9TNNBDmpESWS65CQn50dLbYJFf7RqOmp2AJJMc0nOHUMoLjRBHAtbNfQLgRHeCQaHe7uX2SlPcDP64LpFUMo0hijLDviShPXuOOnUouom-0tl2yzKWaDpi9RNAM1J9IH5F-qU3j7l4ZN5DpiSerc3RnMTd_PijDMcDCNkil8wUBcY-UZGbO56rA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOXVdDAcpkmC0Q*vgkVKCwe8xVJ4mPDz3GgQ3KD-O2Jn8D1TSRuuR76fZBx-N2YEvivwlHf5loZLtWeizQ4Vqfw*Jp93HYynHzU4IWkBJ-DN-BsaZYLUgY*VLoMxMEdnZFk7IMhjrKliu0bEsVFUmgWsOEMUcaJiJbttfCtOxe6Rc=">讲座推荐| <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> for Assessing Health News</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1"><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> for Assessing Health News Quality (大数据时代情报学与情报工作系列讲座)主讲人Bei Yu is the ...</p>
    <div class="s-p" t="1531317420">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt9hlxunDPTkDHhXqV5n8vpk" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzua0rIClBb94AYLLfy0S_EftKRxCiEIoRUPQNB7SX9iSmMHUyDZQ7Jm8s8L6wE9ZClx3-yMEjFER9yIYMsZS7-pBKSVb-l8OVEzc2pGdawkLVrxAM06nvoW4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7lWbNGubPg5K5BWQOibpAo9vQh4JB5UqVqaCSHmafeQVw/0" data-isV="1" uigs="article_account_1">川大公管院</a><span class="s2"><script>document.write(timeConvert('1531317420'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9DEDjs5snc_4nMmXJv7D8-0IKNR5GCe96X2FD4BaUN__8RkhKxdiaPvdnOElsUa5J6W0x-ArGlGAtZNfwvwMkYrPwGGmD02Xo1FzUV55uRNI0PxcfY4UrbZ3Ra9vj1GKbSDaSKR2tk86r6bWG5OCGo_-HDNjAgamfwcAzoIGeC1jP28temKTOwg..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/M47bfSjUwgQr3TusIq60g4nghsj40AiaV838cvFRtHjVMH13ML4NwNSoefmVSzoHTD4062dgg3PJGIqBxBy0QIg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9DEDjs5snc_4nMmXJv7D8-0IKNR5GCe96X2FD4BaUN__8RkhKxdiaPvdnOElsUa5J6W0x-ArGlGAtZNfwvwMkYrPwGGmD02Xo1FzUV55uRNI0PxcfY4UrbZ3Ra9vj1GKbSDaSKR2tk86r6bWG5OCGo_-HDNjAgamfwcAzoIGeC1jP28temKTOwg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOP618VN8DR1IojS*gCijZlEWDU32Cy2Djui4376z9opV4ke46r6YDjW0-isyUOr08aSRW95W6sh3N-7s4qnS3Hu-JiNBd9rRuHFUKO08VNvdhdznMlQtdR-FQuqISK7oPG2KggB5fMJt56qoSXG3GhzzxKHO76ZTdcY3ieSK5kcc="><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> in Action 电子书推荐</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">书籍描述:自然<em><!--red_beg-->语言<!--red_end--></em>处理在实际中是您创建机器的指南,这些机器使用Python的强大功能理解人类<em><!--red_beg-->语言<!--red_end--></em>,其软件包生态系统专用于NLP...</p>
    <div class="s-p" t="1561527833">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFt8yFJv03dCkOU4UQNMITImg" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzRL5SnwLbRrTasLAfZM2OTwfzLp4VgHoPxT7i5R5sCY5zpAxh2ssDJRfKZrbl4KTPQiOQOnf2oGUwqs4UFsTiHSSvVFedkfXC1RtEDTr_KFnXTwxC4ZdtJuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6kmDq8XThnwTWQCwxMtVsu4KF4Ybnia8l1HzAtOeuoiaqQ/0" data-isV="0" uigs="article_account_2">IIBooks</a><span class="s2"><script>document.write(timeConvert('1561527833'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9zPYr8KIK5LXzwn0ZAIELCihsgHjHGMSKPIGvToti5uIX7pCaq8TYCPe3LEPaT7ckUmvgkcqmiutRxGaOlMoyo1qUMCri72U2UnDDak6EuqzjQb_6jGu2YORk8hLuRrsXoCo0WudT8oRWJ9nD4TwW9DprTRR9IWVCn3KNppnWFkTYl_Q5RRZQjg..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/bicdMLzImlibQPcOKDCKpBzm9LQXu46ibia7bHLcRNtYsBeOLzUPn5CcicUjJqvkYfoUibFMNiaQuiaP7BZVHxLPRtngSQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9zPYr8KIK5LXzwn0ZAIELCihsgHjHGMSKPIGvToti5uIX7pCaq8TYCPe3LEPaT7ckUmvgkcqmiutRxGaOlMoyo1qUMCri72U2UnDDak6EuqzjQb_6jGu2YORk8hLuRrsXoCo0WudT8oRWJ9nD4TwW9DprTRR9IWVCn3KNppnWFkTYl_Q5RRZQjg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOPZh*Bau9AuPYj6OPFOQcFhqnqi-yLYv*bRjxoQ35in-1GaDbeWD01Of7BdM9MtX85qsqOqPOkt3W81*nz2Fl8UKREh8AGz3aEpWxylLZbQMWlk7nBoIxESKcTFUBMQgIyf8su10CNyS5LdOSd9iJr1iiWVAXXnbB8BvL-7wD3Uw=">自然<em><!--red_beg-->语言<!--red_end--></em>处理背后的数据科学</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">本文为 AI 研习社编译的技术博客,原标题 :The Data Science Behind <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>作者 | John Thuma翻译 | luyao777 ...</p>
    <div class="s-p" t="1555638590">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFt2sN1DOMaQ5h4Nc4puH3eM0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdz_QngJduzjezLTNLPbDlzszIlNbrRBgc4P8styoR82iqpD0Tb2rFwkgEdLmw8MLI9ndyMbWRw5UlOWWX-l-jGd0Z22j5o2ISnhi9sRVFnUKQI5oPa6-L2sKUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6C2orKhu8vxM7mAt3ibIU19RbSh5BWZh6icOqLysHWWHPQ/0" data-isV="1" uigs="article_account_3">AI研习社</a><span class="s2"><script>document.write(timeConvert('1555638590'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9kalZz9BXgZ1Hfa6cU8kU0AItBm2F8JWSXbU38F6UjgRHK_wHM9u-2RIWCIpGhPSM0Dor0BIxfgGSYvkOsUnVn65CeDKKpagFWPtNTZepDvy1WjsFnmKtS0CgxgxTDfAr6bf454alS0oASSYoznOGylMDsu0LGEtBHLzRTWkuX7XRtmyIGw2VAg..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_png/G8hFes7ezFjuvEPfXMZMicZnmhjLIxZWZGjbUodD7DQ3Fyx9oia14ll9PmRsFiblsUC81DNXx0a8RT9bSGIS5CCibQ/0?wx_fmt=png" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9kalZz9BXgZ1Hfa6cU8kU0AItBm2F8JWSXbU38F6UjgRHK_wHM9u-2RIWCIpGhPSM0Dor0BIxfgGSYvkOsUnVn65CeDKKpagFWPtNTZepDvy1WjsFnmKtS0CgxgxTDfAr6bf454alS0oASSYoznOGylMDsu0LGEtBHLzRTWkuX7XRtmyIGw2VAg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOrOhMKHCQqwHJM65cCvaSNC2HtRutbOc8McuHGpnzmYZ2*E0ijbECbDIT2OP4FW9CjBkGt258hl5nFsXxnqXHguUhEO02gmO2Z28nyt0PZYBuA-0ENt*oNBEbtZMrX-YKH-KHa8OkLUUuPq3G8Nl68MJ0AY74edP0SFuDsAA8Bdg=">Why is <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> important in our society?</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">computers and human (<em><!--red_beg-->natural<!--red_end--></em>) languages, and a machine's ability to understand, or mimic the understanding of human <em><!--red_beg-->language<!--red_end--></em>. ...</p>
    <div class="s-p" t="1557201599">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt6IKtzX4AVlHQzPbD4P-RhE" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzfyCqnhjDugNa9w_Kemup6h2ZcrrQGagWV4Rfmh7kw80o64QQOo5DCFyWbe9MkzUmhW3w3qjU9yWWiPi6N6VwKoFogc0eWUW-ZeE0quT5ClsXyiP2MWoQXWRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6WIeTR7X6uHs5MT94OnGOFibY8VgjGLDmczVMT6up6Dgg/0" data-isV="0" uigs="article_account_4">南风自来</a><span class="s2"><script>document.write(timeConvert('1557201599'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU619-BlllbYaBWMyw7PZmhRGnMSe-bwvcqNdaZs6IpbFXhM7hALETct-QKfHFYjoMmtEjYe-okTdDcg-E2MWR4OP-hXnjm3LMgmOlsi56_O9qaFZMZqHC6yifuAFV_3u-a3OQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AefvpgiaIPw2Kx246g2YibLZ4uoW8yDFLJpuMtu9uaibbtmH1MAPuI8rarByL9STZySy1PvhrrMlauibSoxmEqrTWw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU619-BlllbYaBWMyw7PZmhRGnMSe-bwvcqNdaZs6IpbFXhM7hALETct-QKfHFYjoMmtEjYe-okTdDcg-E2MWR4OP-hXnjm3LMgmOlsi56_O9qaFZMZqHC6yifuAFV_3u-a3OQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOfx8Jfwfb0qSMYPxNYhbrgYI*PUB30WSAbGgkKYoS2Vi4bDKyz8Gk5uHgs0r-PktrDEO-4HC1BAk00lDbnP-JWL4hhnh3mMJ*ecjio74uTIhxFjqxuYpcfXL5ZojjP1444WSR2RnkEfLiusSYGaNFTEyhk96g0l7Qqwk4pjXYKrg=">清华刘洋与邓力合著338页新书《Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">【导读】邓力博士及刘洋博士等人合著的 Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> 一书系统介绍深度学习在 NLP 常见问题中的...</p>
    <div class="s-p" t="1541507755">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt76uwDKxyiHVKwWo3xeOGlQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzOmfPGPvs25f63z-PZUbG8HxQJWHLEey2lB_Az_B87nOJKBnIhqiDW7MGTbU99d_IxbqfApI7PH6BhddYaTtWZ49_3t3UwGebG-3bIPnIJ62DNDZ5j-X_peO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7iathEPUfgnAWr4Hml9INphvANAFNW2LkrRd5RxBqiauzA/0" data-isV="0" uigs="article_account_5">专知</a><span class="s2"><script>document.write(timeConvert('1541507755'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9VNqD2-xO98_Qi9Huq1nNLVAI0Jfbx70aJEWa3xZrb9Zyv0xNEXfkEsn-1TVB7EnuMRIPLVvQ6lx57g6WX3xSGwgeWmi6sHo37jsVFDAMOwgraPuVYxzr91M16CS48Sv5Y3_cmdXxoryDh53LewCJtuE6Bavf-9CPnmu0_2pyYktQL0Hr9Gyd3Q..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/ptp8P184xjxrUHD380RlfbSOVL2BmEsHaHOXgfvsfeFbyFogDTzuo6ia1jfOOU0kIc5UIN9dmGPBXOmp6WTIVhg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9VNqD2-xO98_Qi9Huq1nNLVAI0Jfbx70aJEWa3xZrb9Zyv0xNEXfkEsn-1TVB7EnuMRIPLVvQ6lx57g6WX3xSGwgeWmi6sHo37jsVFDAMOwgraPuVYxzr91M16CS48Sv5Y3_cmdXxoryDh53LewCJtuE6Bavf-9CPnmu0_2pyYktQL0Hr9Gyd3Q..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOwsgaioyf2xviptmdbrxOYgflK6ASaQ1YDQdWZwOwXtG05rUW1OXP51U1WfZLXLk-yPW0GOLsEM16ftECA6Vsz6GYJlvYocxpeY0Yxr7qLNCQJ2md*WmWxliwgee04knoVlV5fcDLPXWubhT4aOAEYAgpdf0BengVNeG5DCa4qY4=">自然<em><!--red_beg-->语言<!--red_end--></em>处理中注意力机制综述</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">with Visual Attention. Kelvin Xu et al. JMLR, 2015.[13] Ask me anything: Dynamic memory networks for <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>. ...</p>
    <div class="s-p" t="1548328187">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFtyJmSw80AxC5wFWs2Vh-bt8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzK9BoU_6AVP5wHDwcXfcG0udRNNDR8KJVicr8My51Y5hq2d5SeTSxuBz0rBUPSSKqPAFeJyhQWwE2_yFnqlMcIuU3NMQBI8geYN8kpyc40d3lR2BS2B1ohKUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM40UKJXCvqrtjIdiaHucmGGe4RBstYzHWS5njG8WaONflA/0" data-isV="1" uigs="article_account_6">人工智能头条</a><span class="s2"><script>document.write(timeConvert('1548328187'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtHxZq_Ef3PYwGJM4K9c25ifU4bRAscvpHLGgsrsBW9Ji3UljvMvNqk-zX4ZjTNzw7eFuyJ2awCWeGi2-iBFq3y73rvnFcX4KTsgMySxYY5pOPwj-dOL8sxyrCDCayYmfpA..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/pmcpibroMBaIhkHIznEbJgVqrWicG5KnAsS0OIgEyFGSicsa1ic8TWgZ0iaibYicpxMYOtSuzLlKicBVwn0ywAbJOdlE9A/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtHxZq_Ef3PYwGJM4K9c25ifU4bRAscvpHLGgsrsBW9Ji3UljvMvNqk-zX4ZjTNzw7eFuyJ2awCWeGi2-iBFq3y73rvnFcX4KTsgMySxYY5pOPwj-dOL8sxyrCDCayYmfpA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOe4CBhTNsLF9L2spwecpO2r*BuHK3NkIyiuqEIV63N7aqj0dSsBBgzi9a25xQWs6sKqrQpdReNZn5-x0rhH72cLjRuUkMSsb3bWYGpxJxwPo54EUb9hzIZFy-V6hW*0ie25VvIG0wQdN3ef2qPFx3HqBIp4dHTFvzRj4JcfGUync=">清华刘洋与邓力合著338页新书《Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》发布</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">1. 导读Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>是邓力博士及刘洋博士等人合著,文章各章内容是一线青年学者对此方面研究最...</p>
    <div class="s-p" t="1541606416">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt7lBT9vr2q6cqd34liXTzPY" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzn1Rs4xw59cha2vK8ZaLsXteyUUjQYI8Wo1MFb2o67h90tCFXVs1SvgrdLij2CvFYOhwcqnivGMEhOYT5I_9gGkIOKwQTEBgNdx_FT-z2GPdHBirK-4t7AuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM49ghiaRuhZbiccUprgby7F1ypb9Agm3QaTIic17vAxvx2dQ/0" data-isV="0" uigs="article_account_7">机器学习算法与自然语言处理</a><span class="s2"><script>document.write(timeConvert('1541606416'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9FsjMGgtebOfoZzxmCxE7xZy0CZsCf9XjC1LIzDhMJT8sH3Lu--mKgVA7Gp9gv1yxtTMZrsPNWFdToI4b3-E5DQ4schI7c6Z-MflHJgl_AbzycBm7qmnF7fLbaq_JNdrFnnJhJQINpzK8TPwt8uWnCWbScNGNRx4v9iX38vs3EI_zAjcIGepUqA..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/KdayOo3PqHBVSZL6Rw2HMpLnqwp9ZTlYwywG1LqyOL9GBmDLcoBPKpoXbBLBtlw4eibmA7hcO9xPHltibyrEb22g/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9FsjMGgtebOfoZzxmCxE7xZy0CZsCf9XjC1LIzDhMJT8sH3Lu--mKgVA7Gp9gv1yxtTMZrsPNWFdToI4b3-E5DQ4schI7c6Z-MflHJgl_AbzycBm7qmnF7fLbaq_JNdrFnnJhJQINpzK8TPwt8uWnCWbScNGNRx4v9iX38vs3EI_zAjcIGepUqA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO1XW5O5ioVMBQ7wVa9TvSnjANpp9Wjw145*ezfcY87gBCAtRzC3J--bOToNT31lcXj8V15zSBVX3QFFa1n*nxyaoyK1iwvxP4sCZIsZYm4RaVulXmpL1qLJmm3BJ5oGCWxTQZhGmBK3CSL3CHULfXyQLW2013HPGMTd7jLVA6g-4=">338页新书《Deep Learning in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">由邓力博士及刘洋博士等人合著,系统介绍深度学习在 NLP 常见问题中的应用,是当前此方面研究最新、最全面的综述. 同时还对 ...</p>
    <div class="s-p" t="1541520050">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFt7riLABrVqn6xhbkX3pqx3o" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzORHDds6diVIMhyg4Y9A9DHE_yksEgKAJmluIaGYOjEJbU-f9qBLV7uVD-U15uPBH8i0RtWSxUb0xC0ixVk8yB0LrEbJPqRi1Fb67WreHO7vwjEiuKY_JO6UiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7N4RJ1VQHdfGXibAMNg7xIMMMfFxpt9t6RxECCQeq6Csw/0" data-isV="0" uigs="article_account_8">机器学习算法与Python学习</a><span class="s2"><script>document.write(timeConvert('1541520050'))</script></span>
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
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtCgRxcebvIOCCy1QmmO7E7Y5UQQ01FsjLjZKFgqj2Sd-ye1wsoImHfxFPaK5AUnKwLrOyT7s1qbjOuflAK3jn0FHMYgNCMGHrwZ5CeT-GzjesRA4v10aKna54z_tGSZTqA..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/lFAia5dnhjrX9xrpHrtlSKLv5I2yZgd13YZAiaeribiaVWyoRA6S4UARY04uMX97wAmdnjdSqnCmQE21uxmByrFIicg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtCgRxcebvIOCCy1QmmO7E7Y5UQQ01FsjLjZKFgqj2Sd-ye1wsoImHfxFPaK5AUnKwLrOyT7s1qbjOuflAK3jn0FHMYgNCMGHrwZ5CeT-GzjesRA4v10aKna54z_tGSZTqA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOe4CBhTNsLF9L2spwecpO2pnX2ByYM8gJpLwViJ4mDy8OTHJqvfTg7PT2rtMVCUQ8XKmyBSOWdcGTG6ZjquJUTYdshz6xdGJOuiclDuHWhxRejtfUs0MGzBXLJEayZYW0rqYJMNnCG1O6BCACbfPEca7qXA28Pm*OnBxIQ4SIDY0=">一起走进自然<em><!--red_beg-->语言<!--red_end--></em>处理的世界</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">重磅干货,第一时间送达自然<em><!--red_beg-->语言<!--red_end--></em>处理简介自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,简称NLP)就是用计算机来处理、理解以及...</p>
    <div class="s-p" t="1552435224">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt7lBT9vr2q6cqd34liXTzPY" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzn1Rs4xw59cha2vK8ZaLsXteyUUjQYI8Wo1MFb2o67h90tCFXVs1SvgrdLij2CvFYOhwcqnivGMEhOYT5I_9gGkIOKwQTEBgNdx_FT-z2GPdHBirK-4t7AuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM49ghiaRuhZbiccUprgby7F1ypb9Agm3QaTIic17vAxvx2dQ/0" data-isV="0" uigs="article_account_9">机器学习算法与自然语言处理</a><span class="s2"><script>document.write(timeConvert('1552435224'))</script></span>
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
    		
    		<div class="mun">找到约100条结果<!--resultbarnum:100--></div>
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
    <a target="_blank" uigs="right0_image_10" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdz_7HLqMzjNmVEiwuoXL0lWRXc8Pg5Cmax8hzKSfOHVuItgZMlOn5trXl2xGZue0t-OmMdqyI14Qxl0aEHSRkBhkNxZi3lWamHvjfF-39VEF-_g98JbR6ALG4OZCnxixtX&amp;type=2&amp;query=natural language processing"><img height="58" width="58" src="https://img04.sogoucdn.com/app/a/100520090/oIWsFt6H0vSmd7OiiNt8fAQlDxgg" onerror="this.src=&quot;//weixin.sogou.com/wechat/images/account/def56-56.png&quot;;this.onerror=null;"></a>
    </div>
    <div class="txt-box2">
    <p class="gzh-name">
    <a target="_blank" uigs="right0_name_10" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdz_7HLqMzjNmVEiwuoXL0lWRXc8Pg5Cmax8hzKSfOHVuItgZMlOn5trXl2xGZue0t-OmMdqyI14Qxl0aEHSRkBhkNxZi3lWamHvjfF-39VEF-_g98JbR6ALG4OZCnxixtX&amp;type=2&amp;query=natural language processing"><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em></a>
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
    <!--1562763692821-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "370ad34a-e3f5-4d6d-9abd-40b0afb75ac9";
            var keywords_string = "natural language processing";
            var sab = "0";
            var keywords = oldQuery.split(' ');
            var now = 1562763692967;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763692967",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "370ad34a-e3f5-4d6d-9abd-40b0afb75ac9",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "5A5AB7DBAFB53DE3F667F13AB0866785",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "2"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-93a24256026c164e6b7db357580e0c6b">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9szbivErKQQMJb2ENwiK9A7agyO3JuKMmEo7gE_Gdf6EhwEiluXouwkNhCJTU_SkUSLByrpuF7ve1vCt7odfMI6uhVU1roQ_03XKgsMLsdPABWiQpmRCb_cFQ4BZTWjLqnv9ULS-ArDZpXOZLn-W7vkQOdpdc-uX8lV5G3yyGKuZ6VKrzu_4XKA..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/KmXPKA19gW8cCllS16e1FuZHMq3Sriam0otyfsiaj6b70ce4H7IFpQKRjGiaKtOHzrLm2ia2t9PibfB1Z71W9L0Siaibw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9szbivErKQQMJb2ENwiK9A7agyO3JuKMmEo7gE_Gdf6EhwEiluXouwkNhCJTU_SkUSLByrpuF7ve1vCt7odfMI6uhVU1roQ_03XKgsMLsdPABWiQpmRCb_cFQ4BZTWjLqnv9ULS-ArDZpXOZLn-W7vkQOdpdc-uX8lV5G3yyGKuZ6VKrzu_4XKA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO12VXWc5T7So3IHmcjQxEYOotXZFrufK3ah*NzTOxxGZkXAA-zEPa*O1Hbl51ecaiDIgnGNLu4eV2YnbWOzCiLq3Pkq4dKaPSMTbcBBY0GjMkummzLPyfKiKJRBnp3PrQsHpZrD8GVwXD10NjzwPV8ce7O3ckiEGvj192qjmE0NI=">深度 | 自然<em><!--red_beg-->语言<!--red_end--></em>处理的一大步,应用Word2Vec模型学习单词向量表征</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">//towardsdatascience.com/word2vec-a-baby-step-in-deep-learning-but-a-giant-leap-towards-<em><!--red_beg-->natural<!--red_end--></em>-<em><!--red_beg-->language<!--red_end--></em>-<em><!--red_beg-->processing<!--red_end--></em>-40fe4e8602...</p>
    <div class="s-p" t="1533102569">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFtyH4wzDYSYFwlcMk8znCtfw" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzRGLZIEUzJX_qOWODnETUR8bTIFw0JvUdInDmj3SPFza0m3lasfxChdRNDh94disQotE5uOuK0PKpJPp9VfuAjyL5f6Oglq5Dh6ev1aix11-P7ElrT2WsFOO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM75UiawQgcdqOcmtYS7Jibug9J7dskxkNicGiadtdKl7mLyiaw/0" data-isV="1" uigs="article_account_0">机器之心</a><span class="s2"><script>document.write(timeConvert('1533102569'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-7948f4c4ae21b43fb7db431ce1f06b38">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU6199o-2ftOkOOT4W-XfKktZFsz579ohzDTB5wcs-HZD7hvmItO3PPVSKUdbsFZetQFx1ZP0kkkwU_miqrtvE4T_gY5PH4tLsGLo9K4ZhDxMLVcuP6D98BNCK3y08OLTBhW0A..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AefvpgiaIPw3a9iaBIMLK0FFHrFbVJUaiaPvYO5sVJehoJQiau1FJJ4p4c1sjBUZkxq5YVt3xxNDSGysic4icEnHtxew/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU6199o-2ftOkOOT4W-XfKktZFsz579ohzDTB5wcs-HZD7hvmItO3PPVSKUdbsFZetQFx1ZP0kkkwU_miqrtvE4T_gY5PH4tLsGLo9K4ZhDxMLVcuP6D98BNCK3y08OLTBhW0A..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOfx8Jfwfb0qSMYPxNYhbrgT4VTPo3oUIMkv-TD0SFAyw2RpbEWKukDpwMw4ZgCu4C0UbGii2AUMlqRo5GedbOFKa83oOWtdEBkv0WNusO3b62QvVngdJ7wVy1IzNQVbC4k*qUA66VS-8kIxc7MadjKaCwY30*aLL9OapAUS9Ufps=">面向自然<em><!--red_beg-->语言<!--red_end--></em>处理的神经网络迁移学习,NLP网红Ruder博士329页论文(附下载)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">后台回复&ldquo;TL4NLP&rdquo; 就可以获取Sebastian Ruder博士论文《Neural Transfer Learning for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》的下载链接...</p>
    <div class="s-p" t="1553394489">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt76uwDKxyiHVKwWo3xeOGlQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzOmfPGPvs25f63z-PZUbG8HxQJWHLEey2lB_Az_B87nOJKBnIhqiDW7MGTbU99d_IxbqfApI7PH6BhddYaTtWZ49_3t3UwGebG-3bIPnIJ62DNDZ5j-X_peO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7iathEPUfgnAWr4Hml9INphvANAFNW2LkrRd5RxBqiauzA/0" data-isV="0" uigs="article_account_1">专知</a><span class="s2"><script>document.write(timeConvert('1553394489'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-c7016926768e05b8391f652d4f6826f1">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9djbCEULjpirW5BrIoQL-HnchffpTnoc_QG9D7Dq7d-xRmnk_tIKYqMsE-k89UaCx9W5Vva2NvivLZw0Kikc9YMOg08rrOBvS-vH8MwmT_VBikf6CJ9lQ3S5nBk-YAp8qJiAzypV-7rC_HDJzNOJPEUdXzSjMmi3tETpC54U5JmtAe0f8bRARvQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/iaTa8ut6HiawAShQwF9OI9df9ibn5ERwcoaFNkIZcibeVC7fjy5PUDIicBClIqD9UTqhPA88K8aOdwAtnTtBbQZiaamw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9djbCEULjpirW5BrIoQL-HnchffpTnoc_QG9D7Dq7d-xRmnk_tIKYqMsE-k89UaCx9W5Vva2NvivLZw0Kikc9YMOg08rrOBvS-vH8MwmT_VBikf6CJ9lQ3S5nBk-YAp8qJiAzypV-7rC_HDJzNOJPEUdXzSjMmi3tETpC54U5JmtAe0f8bRARvQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo-SaADcK1tlMIpFESPAx8qgzTbxSXjyUtJHtj8uhDdY6VCPmt9CTA1jKRSSXUaVvvTtMi4P5ciN9oZUNpzlRP*ZNTTmbAqY2ndK5-Jso0PWbr1i6-ZG096VQoSsCizS7inawtc7xgP7Y9inMta4qJodonzxmiHegOPB7LK0ew*c=">干货|《从零开始学习自然<em><!--red_beg-->语言<!--red_end--></em>处理(NLP)》 -基础准备(0)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">但仔细找找的话也不少(都需要翻墙,手动捂脸):经典自然<em><!--red_beg-->语言<!--red_end--></em>处理(斯坦福):《<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> course by Dan ...</p>
    <div class="s-p" t="1556161239">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFtzl_Teenu6TbOHQse3Z85x4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzYeSPb9xkUsE-UATq4hlTHDaiE6WyPPBI8BsArQCtx8zxDkorOCTOMe1yTtVGSlf1BDOscHVs-EgZFGX68eb0VkNg2L2mSP_1EAfmJ-CWgj1pqF_3ju4EiWRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6yU3rHetd63GogQz6bcZ2TPpP4bibCThe9KJhrrpeP5LA/0" data-isV="0" uigs="article_account_2">机器学习算法工程师</a><span class="s2"><script>document.write(timeConvert('1556161239'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-fda45a8af387c7dd8884d82e6fedc0b6">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9zPYr8KIK5LXzwn0ZAIELCihsgHjHGMSKPIGvToti5uIX7pCaq8TYCC-cqbxl0itSSqzqb_yER2SgUNEBd9zJ-ZQzKr-8u4S-Y6n0R_Uuicl-T_8qznwHSAnAlPaafOKjDs2l90bMRYy-bDsYQwGcFpwfY9N6bcTGeKTvL-zIF1DRtmyIGw2VAg..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/bicdMLzImlibTRnEIDeIUuMicfPTUicz4zf3naO941icAKIKWOLw8JIFKfbXCcYyu0VAn7X4o4ibpyDraib28BzcSP4ibA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9zPYr8KIK5LXzwn0ZAIELCihsgHjHGMSKPIGvToti5uIX7pCaq8TYCC-cqbxl0itSSqzqb_yER2SgUNEBd9zJ-ZQzKr-8u4S-Y6n0R_Uuicl-T_8qznwHSAnAlPaafOKjDs2l90bMRYy-bDsYQwGcFpwfY9N6bcTGeKTvL-zIF1DRtmyIGw2VAg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOPZh*Bau9AuPYj6OPFOQcFhqnqi-yLYv*bRjxoQ35in8Ky7klndw3usiJXPcI07k1j8nkeqi1PFGxtvARPOJbGVvGr9YpXCLuTnck3V0TU7*R-8yHoFQd-eS*7dSk38vjWU7skGU9142N37n2sp39g1AXvnmOZ4G3b*HbEHcZ658=">一文带你读懂自然<em><!--red_beg-->语言<!--red_end--></em>处理 - 事件提取</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">本文为 AI 研习社编译的技术博客,原标题 :<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> &mdash; Event Extraction作者 | Rodrigo Nader翻译 | 胡瑛皓 编...</p>
    <div class="s-p" t="1557483904">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFt2sN1DOMaQ5h4Nc4puH3eM0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdz_QngJduzjezLTNLPbDlzszIlNbrRBgc4P8styoR82iqpD0Tb2rFwkgEdLmw8MLI9ndyMbWRw5UlOWWX-l-jGd0Z22j5o2ISnhi9sRVFnUKQI5oPa6-L2sKUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6C2orKhu8vxM7mAt3ibIU19RbSh5BWZh6icOqLysHWWHPQ/0" data-isV="1" uigs="article_account_3">AI研习社</a><span class="s2"><script>document.write(timeConvert('1557483904'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-f2fb7e5d238f97fa598ec7bfcb1efa21">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9qLWyHGirUjplgnWp8F-QUTQKwSIyVzw38pLY0q9FhNhzV8RAIku7GZtm0LaxWCmWKSm6mcept3s3TcPbv-w7Adi245eDFjmbnEw0BbVohSnAV3_CHjEdEPm3AmHqa83IBw4YrWnCkFma1_6DmSbuayDlcyDcsrf7hoK0tGC7ej3I3OTRHYU2og..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/pxMrQvgWLUKCg5uvLCGYTARQ0ZgTWnKTtgibcwB4YGABn3MeZMu69HyYAhxlUVclSMicklf2r17grdFrsJuCUCbA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9qLWyHGirUjplgnWp8F-QUTQKwSIyVzw38pLY0q9FhNhzV8RAIku7GZtm0LaxWCmWKSm6mcept3s3TcPbv-w7Adi245eDFjmbnEw0BbVohSnAV3_CHjEdEPm3AmHqa83IBw4YrWnCkFma1_6DmSbuayDlcyDcsrf7hoK0tGC7ej3I3OTRHYU2og..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOY9B8teImlll6qH9YXZs73JIehT01q4*bIMmkH-9sCLD95Mr68qSz*JXwe29EDHUvUqxW9VweiemlemRG4Mx37yYBKtkofKpptM3HJjw*z4HVIb2RV1by3bU2koVHgCy6jRILth2uX4hk2WBgl1E9rEIHJXRZdxNDCXDGT3q9s*Q=">自然<em><!--red_beg-->语言<!--red_end--></em>处理背后的数据科学</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">相关报道:https://medium.com/dataseries/the-data-science-behind-<em><!--red_beg-->natural<!--red_end--></em>-<em><!--red_beg-->language<!--red_end--></em>-<em><!--red_beg-->processing<!--red_end--></em>-69d6df06a1ffCDA 课程咨询丨赵老师...</p>
    <div class="s-p" t="1556536448">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt0I84lFFKxvojr4PYPDvRqA" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzl4EhkDY5LsOQr82hLY_6OQiJT19wZcY6mkfzgbh5J-lSQ773XYgRWEplmKXn_s32Pr_Yz6matK_YfkKB3muqy1VO_MotElBxHI4yvl6znycm384vG6ElD-O00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7Dbfiado7omniaUnhKRUudsuJNvDqTBgwPzqH1Ficp7Th7g/0" data-isV="1" uigs="article_account_4">CDA数据分析师</a><span class="s2"><script>document.write(timeConvert('1556536448'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-5fd08f8ed830c5c69f4a0f0af85a5cb0">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtPLUqK8h4BbaYMbL-fpL3nmxc_KZYgf0hvqAMgP_IMfl3S0Y0Dt6voBpGMH4Mfn2dbCC537rhZk9i042Y1uwkOQzgFZSv2Hb8CQLOzTGlIyijRjLYFlQYirYl_Q5RRZQjg..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/bicdMLzImlibQJgjuG4og4XDNFxxwswQMdbicGNq1Fbh17ia5cFOv5h31UDpwwvw1DKuT3YKRP7u6smQibhvmlCLccQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtPLUqK8h4BbaYMbL-fpL3nmxc_KZYgf0hvqAMgP_IMfl3S0Y0Dt6voBpGMH4Mfn2dbCC537rhZk9i042Y1uwkOQzgFZSv2Hb8CQLOzTGlIyijRjLYFlQYirYl_Q5RRZQjg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOe4CBhTNsLF9L2spwecpO2pnX2ByYM8gJpLwViJ4mDy8cNAZBDYfj5yduhw4kgrivx001405lYx1egWnwdWA*2QQWBNrkh9uQsV1oanuhWdL3r9YIIjUr0HHohRpDRd0sE4UjuUCPyYz6RJLqGODgqlxy2vtzLyFpTkG7iVpplOc=">EDA:最简单的自然<em><!--red_beg-->语言<!--red_end--></em>处理数据增广方法</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">本文为 AI 研习社编译的技术博客,原标题 :These are the Easiest Data Augmentation Techniques in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> ...</p>
    <div class="s-p" t="1556380851">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt7lBT9vr2q6cqd34liXTzPY" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzn1Rs4xw59cha2vK8ZaLsXteyUUjQYI8Wo1MFb2o67h90tCFXVs1SvgrdLij2CvFYOhwcqnivGMEhOYT5I_9gGkIOKwQTEBgNdx_FT-z2GPdHBirK-4t7AuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM49ghiaRuhZbiccUprgby7F1ypb9Agm3QaTIic17vAxvx2dQ/0" data-isV="0" uigs="article_account_5">机器学习算法与自然语言处理</a><span class="s2"><script>document.write(timeConvert('1556380851'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-0b0d24566bd694bca33413b34ceca049">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtBZRC_bjHmjdtR_CafXz3D393wOZ2lBPYoTPaDeYj0oZfz5Br8J2oXveCZpJLztrbf1SHHT1RBk-G2asoFETw81IeqjzBK0IoI6wfNidbMCIy20OWh3S1hj1AfaFW2DefQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/lFAia5dnhjrU5JCgxglKCcJtSpZ7fUaYZfbMDyGN6HDLicHL4F1xbZH9t7ZiaEI3red5U359Mc0A1RFqoorodvFeQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtBZRC_bjHmjdtR_CafXz3D393wOZ2lBPYoTPaDeYj0oZfz5Br8J2oXveCZpJLztrbf1SHHT1RBk-G2asoFETw81IeqjzBK0IoI6wfNidbMCIy20OWh3S1hj1AfaFW2DefQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOe4CBhTNsLF9L2spwecpO2pnX2ByYM8gJpLwViJ4mDy9WlBEpq-DSsofVV1XfuUMqTWKjBeCTAdyFjoZk9-6jrttgfDcFdU9qqBkWoDq*K5W-unwbyP99qq7RTpKiKtwFdJCBNyjCTAWnjbAM91KXg9yWwxhUuxIEmTyCMK4WDjo=">资源|PyTorch自然<em><!--red_beg-->语言<!--red_end--></em>处理实战(附最新PDF,中文翻译笔记,源码分享)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">原创干货,第一时间送达一、书籍简介本书《<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> with PyTorch》于2019年2月在美国出版.自然<em><!--red_beg-->语言<!--red_end--></em>处理(...</p>
    <div class="s-p" t="1555326012">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFt7lBT9vr2q6cqd34liXTzPY" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzn1Rs4xw59cha2vK8ZaLsXteyUUjQYI8Wo1MFb2o67h90tCFXVs1SvgrdLij2CvFYOhwcqnivGMEhOYT5I_9gGkIOKwQTEBgNdx_FT-z2GPdHBirK-4t7AuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM49ghiaRuhZbiccUprgby7F1ypb9Agm3QaTIic17vAxvx2dQ/0" data-isV="0" uigs="article_account_6">机器学习算法与自然语言处理</a><span class="s2"><script>document.write(timeConvert('1555326012'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-5984f245a30705cf4717ef2349d1c3cd">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU6192npSViY3CXssqIJdOFalI6d9PkwgGlJ_RKpKWCsBbDgerkTCI3iiAy_W9FUEJcEwKyQeTSaTR3iHWO_m9iRdA-iznXonIt7zefFkv0XxhV41xygB27uNPxhWLv6O878UA..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AefvpgiaIPw110XG3HWwxsVrmvjrORIWPNB3nGrApsbzicTp7v4BnSsQ9RCIcgEpQ3vUsrLAuX9mu3ndGKsRmSrg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU6192npSViY3CXssqIJdOFalI6d9PkwgGlJ_RKpKWCsBbDgerkTCI3iiAy_W9FUEJcEwKyQeTSaTR3iHWO_m9iRdA-iznXonIt7zefFkv0XxhV41xygB27uNPxhWLv6O878UA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOfx8Jfwfb0qSMYPxNYhbrgc6vhXk9ZxVFX179VGTK6HSjDk9pST60n9AJf3cMqjxg-he8Qrr42GZgm8dpc3WA1szsmmAa3bN5egnqGc0ZlUiuzrzAcNiU7yAORdqhsLA83X04mEHOh41ds0ZJe23bUObOCJaXPn*NH-16y*hr2q4=">【干货】33页最新《自然<em><!--red_beg-->语言<!--red_end--></em>处理中神经注意力机制综述》论文</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">《Attention, please! A Critical Review of Neural Attention Models in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》,详述了最近几年NLP任务中使用...</p>
    <div class="s-p" t="1549770981">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt76uwDKxyiHVKwWo3xeOGlQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdzOmfPGPvs25f63z-PZUbG8HxQJWHLEey2lB_Az_B87nOJKBnIhqiDW7MGTbU99d_IxbqfApI7PH6BhddYaTtWZ49_3t3UwGebG-3bIPnIJ62DNDZ5j-X_peO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7iathEPUfgnAWr4Hml9INphvANAFNW2LkrRd5RxBqiauzA/0" data-isV="0" uigs="article_account_7">专知</a><span class="s2"><script>document.write(timeConvert('1549770981'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-360d2e665d7abd85f9a02b880dcb6341">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9nqYnz23Ng7RMA179ukVDI69SSkDiMGemctEnEb1BfjBVrUKEM94bl2-Ow0C6-fsRd-XEBrHcI6uoC7K3nk9taDUjrqo07ubxpIfESFnu0M37CDNR9I8zVeR1vR74SWQ6jaYxQWIv9h9iVJ8TZCLZbKk82efz2xEtmg-3XFAHAksCn9lOoZLP2Q..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/lFAia5dnhjrUSjIW6gmAjPUZ1dMs4iatEbBqunKVibfiaQew8AGBoLGT2N6EIR9QcZibgeKaSaqIiaH8O8LJ8chib5x3A/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9nqYnz23Ng7RMA179ukVDI69SSkDiMGemctEnEb1BfjBVrUKEM94bl2-Ow0C6-fsRd-XEBrHcI6uoC7K3nk9taDUjrqo07ubxpIfESFnu0M37CDNR9I8zVeR1vR74SWQ6jaYxQWIv9h9iVJ8TZCLZbKk82efz2xEtmg-3XFAHAksCn9lOoZLP2Q..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOrXXy6QWmHVZN-BrJSqcyK2-15KTsVUf99ydRMQ24N*vlHKpBfCFB*3vvqqheRlDOZAzM6pGm04mOjFJO5iXkedeNNbtAHUTAcJBShBGe0orwgO7QAxmp2ZWUbpZkX100hMN7APaj5RuUmEerBMxCXkn99xYFbnQi6mHtNDMG*Ns=">干货|最全自然<em><!--red_beg-->语言<!--red_end--></em>处理attention综述</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">with Visual Attention. Kelvin Xu et al. JMLR, 2015.[13] Ask me anything: Dynamic memory networks for <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>. ...</p>
    <div class="s-p" t="1561770046">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFtw1cI31ORa4g6oVE6V0-7tM" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdz4BZIMcvlrRwdIW5TkZ9-tMF4xNZtRG49CYmyu0Ku-WhqCjb1cZ2D2SqEDNU9TxXyA5B6qKLYBEiEgY6fIGX-RK5bpQW70BuASJwNcIAj3xMJk9lJv4ZNjW4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5vkJRATnZicFQpicyfmhfMFpicInSefvktsbVyst8oq5Eibw/0" data-isV="0" uigs="article_account_8">AI遇见机器学习</a><span class="s2"><script>document.write(timeConvert('1561770046'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-acaa35dd70a1755046f94a352a4d4189">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9zPYr8KIK5LXzwn0ZAIELCihsgHjHGMSKPIGvToti5uIX7pCaq8TYCKgctuCbzq-JdQZI07Y6u5vQNRsT0BQV5g6-k3l_y8-KrFlWcr0Vj9vLNj_1XoFCbvB5odsG990II9itQSS1ry1ASJfyoLaRMGmztOCi-5IYTCCETglSsWT0OK9DLfgmPA..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/bicdMLzImlibQJgjuG4og4XDNFxxwswQMdbicGNq1Fbh17ia5cFOv5h31UDpwwvw1DKuT3YKRP7u6smQibhvmlCLccQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknWI2R3mdhGWQayZY1qgS8UV1qXa8Fplpd9zPYr8KIK5LXzwn0ZAIELCihsgHjHGMSKPIGvToti5uIX7pCaq8TYCKgctuCbzq-JdQZI07Y6u5vQNRsT0BQV5g6-k3l_y8-KrFlWcr0Vj9vLNj_1XoFCbvB5odsG990II9itQSS1ry1ASJfyoLaRMGmztOCi-5IYTCCETglSsWT0OK9DLfgmPA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763692&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOPZh*Bau9AuPYj6OPFOQcFhqnqi-yLYv*bRjxoQ35in8XSdrbIvrq02*ytnIlIrPYK4B80fzOgmUgEPjkNTqx6KKXNr*y2cqSltjNlHNoQevg6TxjmN2Q2ac1WxHrukWcSAf-exMz5mqRTcMSvzhgdzJ0GxdfZfvVVehJqehFJhA=">EDA:最简单的自然<em><!--red_beg-->语言<!--red_end--></em>处理数据增广方法</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">本文为 AI 研习社编译的技术博客,原标题 :These are the Easiest Data Augmentation Techniques in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> ...</p>
    <div class="s-p" t="1556416678">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt2sN1DOMaQ5h4Nc4puH3eM0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdz_QngJduzjezLTNLPbDlzszIlNbrRBgc4P8styoR82iqpD0Tb2rFwkgEdLmw8MLI9ndyMbWRw5UlOWWX-l-jGd0Z22j5o2ISnhi9sRVFnUKQI5oPa6-L2sKUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6C2orKhu8vxM7mAt3ibIU19RbSh5BWZh6icOqLysHWWHPQ/0" data-isV="1" uigs="article_account_9">AI研习社</a><span class="s2"><script>document.write(timeConvert('1556416678'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=1&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a><span>2</span><a id="sogou_page_3" href="?query=natural+language+processing&type=2&page=3&ie=utf8" uigs="page_3">3</a><a id="sogou_page_4" href="?query=natural+language+processing&type=2&page=4&ie=utf8" uigs="page_4">4</a><a id="sogou_page_5" href="?query=natural+language+processing&type=2&page=5&ie=utf8" uigs="page_5">5</a><a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=3&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约100条结果<!--resultbarnum:100--></div>
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
    <a target="_blank" uigs="right0_image_10" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdz_7HLqMzjNmVEiwuoXL0lWRXc8Pg5Cmax8hzKSfOHVuItgZMlOn5trXl2xGZue0t-OmMdqyI14Qxl0aEHSRkBhkNxZi3lWamHvjfF-39VEF-_g98JbR6ALG4OZCnxixtX&amp;type=2&amp;query=natural language processing"><img height="58" width="58" src="https://img04.sogoucdn.com/app/a/100520090/oIWsFt6H0vSmd7OiiNt8fAQlDxgg" onerror="this.src=&quot;//weixin.sogou.com/wechat/images/account/def56-56.png&quot;;this.onerror=null;"></a>
    </div>
    <div class="txt-box2">
    <p class="gzh-name">
    <a target="_blank" uigs="right0_name_10" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_9oZUiAfRNTVgwvDqyjOWdz_7HLqMzjNmVEiwuoXL0lWRXc8Pg5Cmax8hzKSfOHVuItgZMlOn5trXl2xGZue0t-OmMdqyI14Qxl0aEHSRkBhkNxZi3lWamHvjfF-39VEF-_g98JbR6ALG4OZCnxixtX&amp;type=2&amp;query=natural language processing"><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em></a>
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
            uigs_para.exp_id = "null_10-null_11-null_12-null_13-null_14-null_15-null_16-null_17-null_18-null_19-";
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
    <!--1562763692967-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "c930a303-dd8e-47b1-893f-2f2c82c1b7d1";
            var keywords_string = "natural language processing";
            var sab = "0";
            var keywords = oldQuery.split(' ');
            var now = 1562763693054;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693054",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "c930a303-dd8e-47b1-893f-2f2c82c1b7d1",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A52922C6E42F2EFA",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "3"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-7232d3eb0025edd33b5e0e6ab476ea9c">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtJ0ZGl-dgfD5mkw2efNa4RvKIsZP3-URdm2jX1aBmBdbq-R0LZNuomTviFdbwozU1GOUSebJ6qzGyjmTREG_RsOCbljAtFUI1WkvzLTNKBszmZWoYcebhkgC2Qmj7RgGwQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nJZZib3qIQW4pGCkmuV5Sib8X8TDXTl0uu7IdDZbfQwHlLZicMXcmBz0BUDl7T85ia9Qr4bHPiajo8nSoicUQfJQad6A/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9725Vds1pF_gcM7riUVS9USil7PNJiUsEyIeFrZtgVKAeLW4SX5PNtJ0ZGl-dgfD5mkw2efNa4RvKIsZP3-URdm2jX1aBmBdbq-R0LZNuomTviFdbwozU1GOUSebJ6qzGyjmTREG_RsOCbljAtFUI1WkvzLTNKBszmZWoYcebhkgC2Qmj7RgGwQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOe4CBhTNsLF9L2spwecpO2pxvR52L*o40dFUqg6HsXEKRVRfeJlTsv2sk1eeNy9sO0Ux3wtc*OtkDaAqVCtB7gzQnWqqXk9MAvI1-Elg0bIdrU894yLmbqToKSQnN03vK6swswzAp9CCQHJmKBHNCIbK6eismQ8Y9MVuWkIKcKCU=">资源 | 初学者指南:神经网络在自然<em><!--red_beg-->语言<!--red_end--></em>处理中的应用</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">「基于神经网络模型的自然<em><!--red_beg-->语言<!--red_end--></em>处理入门」(A Primer on Neural Network Models for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>).对应的论文 2015 ...</p>
    <div class="s-p" t="1505692821">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFt7lBT9vr2q6cqd34liXTzPY" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzn1Rs4xw59cha2vK8ZaLsXteyUUjQYI8Wo1MFb2o67h90tCFXVs1SvgrdLij2CvFYOhwcqnivGMEhOYT5I_9gGmASkuiAvHn4umStB8noLxZNvq7tK00Q_KUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM49ghiaRuhZbiccUprgby7F1ypb9Agm3QaTIic17vAxvx2dQ/0" data-isV="0" uigs="article_account_0">机器学习算法与自然语言处理</a><span class="s2"><script>document.write(timeConvert('1505692821'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-1fd6fcc7622500136ff3997821f3cec9">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9XI1xExQ65GH6MmHzYgUnCC0sxDuIpFwzj5CC1a7c1kICN8xgqmTP_BYfimUx--9n3B0T2LZjV_0XyaIu-ms9FO8IJLi-0YNvcv85yuKZjIgAzh3WVNt7-pNqV8P6QOGRFjHtGdkiA_KzxbRFFaptx3Dw5YoBAeRyNfcqW8yLkmb1AfaFW2DefQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/667nlEyAYYibOotDaYticItnIoicC576VNc3yibrcKYib7C2HqwicLstwhfXxV4uOolYPWkr1XvKq51v0viaL4caIaMZA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9XI1xExQ65GH6MmHzYgUnCC0sxDuIpFwzj5CC1a7c1kICN8xgqmTP_BYfimUx--9n3B0T2LZjV_0XyaIu-ms9FO8IJLi-0YNvcv85yuKZjIgAzh3WVNt7-pNqV8P6QOGRFjHtGdkiA_KzxbRFFaptx3Dw5YoBAeRyNfcqW8yLkmb1AfaFW2DefQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOgmeSg-cM9eMeDV0UgdrfjR9iEe6Zvmcx0KtpOY*smhClv-VmB-LLnenc9Df2g7R44UUOtJn19GtIFV4j*yD74R7daDIVkO336whX5Rihvbs-003p0WOTcdCxh50x0RpY1W1b1Hof6jbSkvI3dJ1iTvFBFj6ep*6eD7Rn3szJWvE=">达观数据:中文对比英文自然<em><!--red_beg-->语言<!--red_end--></em>处理NLP的区别综述</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">攻克文本语义对实现AI全面应用有至关重要的意义.相应的自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,NLP)技术因而被称为是&ldquo;人...</p>
    <div class="s-p" t="1552987824">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt6mlSteOWvYYmFta63du408" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzg_P2XZ903PT1QypUHv1Bnu62bmr77NYYN5kIOKrzsvV3caXFDpE42bzsXFP147lWn7LrpvfB-qAp4F5jV9hkDL5lhSCGHnvvpXrkvuD5ryswaoa6mZW3BaUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM60l5seVpP8vVicCrMpxJovdqNw8LR48o3RT3pQSLCm0ow/0" data-isV="1" uigs="article_account_1">达观数据</a><span class="s2"><script>document.write(timeConvert('1552987824'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-986b524e7b539cc72235a5c5c99a4d2c">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9vww34qvVYPXGT1Lc24fRJLzcWMwSpz_L19aO4-UE4yTCdbIzNHhQdAuuBgfjPaDF7YY381ZOUBCdfTOny3f__VnN2WGXOLVn4sQJ10wvlVulB9VYCSbM62w4Kh6I0tuZ_O17Kpfw74b9c9XOERQdOjx8bC_BlxgoBSKvTSU8QlaTJmCU1UgHwQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/sUAjH85EPNVEUvUdM9D6kfLdwFM7LbBPmqLYyXIXfFtelFsRHZZ7krX5tPjzGEyNMIyFBSFm2grlJzBDV3brQA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9vww34qvVYPXGT1Lc24fRJLzcWMwSpz_L19aO4-UE4yTCdbIzNHhQdAuuBgfjPaDF7YY381ZOUBCdfTOny3f__VnN2WGXOLVn4sQJ10wvlVulB9VYCSbM62w4Kh6I0tuZ_O17Kpfw74b9c9XOERQdOjx8bC_BlxgoBSKvTSU8QlaTJmCU1UgHwQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOZlKVKNASIWbG8chgFi5K75TddwGYYIsFtQXN1bhsJz8NGM1996jtH8HWf7Kp4Eb7NJa-Tem1L2*LzQM8Wk-f8Vr6x9ZUbiZlZnlCZdm2sbcWOehfy9lMZeA5jxznoZBDMQVgFVfWy2fVh8Gw0e6F464eYSxsJVG7Nnd6qa7iLPY=">应届 |【IBM】Data Scientist - <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em></a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">【香港应届】IBM&mdash; Data Scientist - <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> 要求具备1-3年的机器学习算法经验 申请:阅读原文Data Scientist ...</p>
    <div class="s-p" t="1555381818">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFtx8W8u6vLEhCVMx7zX5C_sw" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_MNfhSRgCLAzlbzStfeiCQIQmsdr8rtD0zQ6xa_bWlFg9BwPi5Z5eYPzALujE2XayUSKKkuZC9ds0_NPlCLbbaD7K6wPjp11Bb8aUHRkR3No2NwM4asXjG4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM551gQViaic3Zic5BpASCia5bDic84FuPPiaN2ibkR1a5y6RNCAw/0" data-isV="0" uigs="article_account_2">香港求职</a><span class="s2"><script>document.write(timeConvert('1555381818'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-45d02623b6102ce557e83fce5cc13fc4">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd92xqLRl8G_AT9sKWjlrnXCQEAoEVXmRAfm2QTIBK--tHmU0hyImEUKgPcO04wmmYtOz5bjJB8NRZYvUwikZjMilv7yv_0aP0M-2Of9R1idr7a7Dfg7pFXCOU3GTGNbQNSPUUYF3MzmnQv2BE8pilArfBSgeSXhiu8-MKrWTfzr2gNGbbB75bUeA..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/HicsOQIbsWbPBxQVicefgR2tajnTyutSyulTHjyBrSfPaTftEFTJE4DLvzicuJrmd1U62YMaA52tzNuVwdQiaDQjiag/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd92xqLRl8G_AT9sKWjlrnXCQEAoEVXmRAfm2QTIBK--tHmU0hyImEUKgPcO04wmmYtOz5bjJB8NRZYvUwikZjMilv7yv_0aP0M-2Of9R1idr7a7Dfg7pFXCOU3GTGNbQNSPUUYF3MzmnQv2BE8pilArfBSgeSXhiu8-MKrWTfzr2gNGbbB75bUeA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOa0CQpXMkQSO7TSzVCuobIsIMSBlE0vBJjApVKTZVhVtkPOZ7mX9eBaol-RZwJL1wzaU2z1EtyV*LTseETNdgaECc83cXY3HIRgiUOWS7cuzeYn-Ul4a3oAxXuZPsTKgqdDj0We6Gm5grpOWuV4mwi2xWCjyjlbbBkdj-YSD9dIo=">自然<em><!--red_beg-->语言<!--red_end--></em>处理每日论文速递[06.07]</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">【19】 Survey on Publicly Available Sinhala <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> Tools and Research标题:公共僧伽罗语自然<em><!--red_beg-->语言<!--red_end--></em>处理工具...</p>
    <div class="s-p" t="1559873826">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFt4PZk75Z_xIiitBxEhu1HU4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzcbHgKoukdvcLWYCafyZHCFW70xqtL5T4HbQEFY0G8P-SMZpoZE1V5qVoz2EnseIIatlRYh-OMWBXwMSoIpsFscjxljJSgHiOiWSz-0GBMEOq-SYB2bDUGKUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6u8u8Rd7gUkwyEBMa5ZCCoQ4L1GgSCfFm8VRMEHYeEpg/0" data-isV="0" uigs="article_account_3">arXiv每日论文速递</a><span class="s2"><script>document.write(timeConvert('1559873826'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-637f4aaf976eae6259cfb411abc64561">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9gByKrumYUdSr1TYjpHoAGKDARL5elAdFzi8brwS-x3pFiFg3-6rqsohBeFrkBlOdcgG0RI2VGotcwymaorJCOxK8OBswfq9aa_hu0YX9QkzHW-vZiPoUQIaV4TRZCa8KA_GmQqAna0WeadZ8yS7si2PTJ-phKyHNpiIvy7P-HGHzAjcIGepUqA..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AZAS1zcT0cAjDghyG56kuJy6wBcaP92nDZPC3alRZOL6f3Vb4wJ46LcgbHMUctiaGr6Jd89QBjP4o5ELu9tSBmQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9gByKrumYUdSr1TYjpHoAGKDARL5elAdFzi8brwS-x3pFiFg3-6rqsohBeFrkBlOdcgG0RI2VGotcwymaorJCOxK8OBswfq9aa_hu0YX9QkzHW-vZiPoUQIaV4TRZCa8KA_GmQqAna0WeadZ8yS7si2PTJ-phKyHNpiIvy7P-HGHzAjcIGepUqA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO9G-MYyoIr2vsd8e2SOB77w7R-6HY4Lj4hOZ5tCLGY752GcNth0ZPktFDEy5q-PAvGnCuBmxL9x*xv1HgJNBqnQ8DAyMM9gialNQfTKX9zIhz2OPPdQuJEwAO7GAGf26OLehnba90bhLDsV3z82zyg2Rjf8bzci10cFSMQTazefE=">最新发表 | Chersoni 等(2019)in Journal of <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em></a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">P. Blache, C.-R. Huang. A structured distributional model of sentencemeaning and complexity. 2019. In Journalof <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> ...</p>
    <div class="s-p" t="1560136119">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt5LBA9D7IiCfVrIxVkgeFMw" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzG14S0CJzT8gMbNUhjUKegFo9BNqaFPNlmYYWS2Ru92czeqn0yazVU1aiEnT3NmWsdQ1gh4nDNHf1hTtdo-pSJgq52e5FpGzF-YPnxh5yWPDs91K2la5LAqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4xB4aBVgRF0VnRe03aER4EthRknvgWRSMeL6p8Lgsic2w/0" data-isV="0" uigs="article_account_4">PolyU LLT Group</a><span class="s2"><script>document.write(timeConvert('1560136119'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-08fbc0f73edaa890b94fa51c062710ef">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9cTPL55wkxOQw2MAHl_nXRrLPyZIFJkEU7F6c0mEC7OiZfj5ggOcdOXCC1T7yh188Rynfp95L3dJlRJCpnZh54iIvFsUQp8xi9tv_VwpVUYYUYnHEwURcmTrgkWNH4sjI6VLaN2PWNoTd1-tWkTWk44aU5Hxq8e8n--SqMZnmN9dhlgeRt7bSzA..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/t347c1sr9mZ7pYOK4VcUK3B27l2BVoiaS2UVOkd9OHRQeunescXfLnoX9ZHGPDahvYUQeEIPiaoU5VlZ8OvNZibPw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9cTPL55wkxOQw2MAHl_nXRrLPyZIFJkEU7F6c0mEC7OiZfj5ggOcdOXCC1T7yh188Rynfp95L3dJlRJCpnZh54iIvFsUQp8xi9tv_VwpVUYYUYnHEwURcmTrgkWNH4sjI6VLaN2PWNoTd1-tWkTWk44aU5Hxq8e8n--SqMZnmN9dhlgeRt7bSzA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO-B0zCAKRcdB22xevCAhPnjW8gEv8MVaSagLnGah-7yKRbt-wgK-c0vY1uByTLukktIJFPcVUQtze*kUYQxPpfeek27F*uUUWUY6DYJmrKc*vF9L5vAT1Y4X3psIKM-fqGovsJzT*kVlk87OtPq*c2-*qtsNGMhwJZttQNx*l6gg=">5本自然<em><!--red_beg-->语言<!--red_end--></em>处理书单-附pdf | 书语</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">自然<em><!--red_beg-->语言<!--red_end--></em>处理(英语:<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,缩写作 NLP)是人工智能和<em><!--red_beg-->语言<!--red_end--></em>学领域的分支学科.此领域探讨如何处理及运用...</p>
    <div class="s-p" t="1558677550">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt2GzsLHpfv68ZwCFTvK3Qys" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz2yQbpFh8PT6xqRVwFSHg2zLhBRguniCaO3J9dCGRPTfEMmXFWh_2YpEMWtg-J8jB-ASGJ1sU573iwK-blR2kDivXg64BYPLtcPJc1wneYwozrtK1eJcsl-O00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4Zcm2UwJtA3hic6Cib5MhPRbpF7MUOvdIsxSficJn4BBQjg/0" data-isV="1" uigs="article_account_5">数智物语</a><span class="s2"><script>document.write(timeConvert('1558677550'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-f5e7692e009b70824ae85fded500ade7">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9P1_rLLVntyiDBvnhKgSztKpsdNkWN563cpf_IV6ak9_XYig6jz4DolERAtBBbqeN2a6qYEqndxTMekHiSDMvGfD2BLMsZ3FnyOhS8jpWs33b8Wko5W6Prt1rU7WVNWnak3N6M9V7r14f3yiI2Y2BvN1HOQvRNENH52GZPCDWuC-q3X8EKMKOIA..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/wExjdy0qvVB5QwnHpBegtSpTbTD9FxLtz2gbQmwcujMgdiaQicr2flhNx1Bu1RpoAzh7yVWFM2OrrN4JZNMb4iauw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9P1_rLLVntyiDBvnhKgSztKpsdNkWN563cpf_IV6ak9_XYig6jz4DolERAtBBbqeN2a6qYEqndxTMekHiSDMvGfD2BLMsZ3FnyOhS8jpWs33b8Wko5W6Prt1rU7WVNWnak3N6M9V7r14f3yiI2Y2BvN1HOQvRNENH52GZPCDWuC-q3X8EKMKOIA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOr5Isz5ATNa3JgWmhaf*CxUXhjoMT5ip7L*yQJNWDGQa3frgsFIizeWfaGZkZIJbI1H2z2ljO-YocBCBlTkSEno46euwxbdmUXQEBcUmiLdQemxmXqzwekFGsRr8qFI2JPYoxKyJ0b2igzx6E4NeZZe7cpE5Jxi97ft7OjPSypLA=">应用 | CNN在自然<em><!--red_beg-->语言<!--red_end--></em>处理中的应用</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">最近我们开始在自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>)领域应用CNNs,并取得了一些引人注目的成果.我将在本文中归纳什...</p>
    <div class="s-p" t="1562248269">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFt2lFkaq8vLlMc2cuULLWKI0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzNwpAhvRfeMhIcigf9nMR941Cs4_lGERK0QjhICPnpzOIp6DCCjlB64dLtZyX0di34i_MBPHIcp1y7q3f-3TNMZQjI3xcst1QOrRDOSOdf-93PjvqHRzZlG4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4gTUEtXQSibV13fvGkU3LZ1FAnx99dWOa8rSWVjtibs4fQ/0" data-isV="0" uigs="article_account_6">智能算法</a><span class="s2"><script>document.write(timeConvert('1562248269'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-f1c5b97558555d2af224fbd116046a5c">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6ft3wfAVofsP5Peu-UiA4DFarRdcj931yH0S3dOME6VyVgrFeYQugDmjb6sixVnAQtLk4yaLoQpUWoiob6N36h3fdNaSPTVVPfRitrFO3fHXS4XXS7lUNSOX7rRmIHw-2wz4W9Olnisjp_F7fLANOKzd1XEYpc3Tmr7gn2VEQIEzp-66-yhzOPuCgObMTxk_cEifX1Uj3otgPpksHp_GOq8FeDL9dZYQjCOpfuLV4_hyU9HSUDv5FMfg5a83JLbqn3nwCeKiTltI.&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz/JAGAAyoQ3akl4CGlmktdPhicjm0tnk7zTl35MXKuOhZYnIr6YZibMibEUZ9IHx2n6c4GhSxUelgfRlAzyibp1Lwa9Q/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6ft3wfAVofsP5Peu-UiA4DFarRdcj931yH0S3dOME6VyVgrFeYQugDmjb6sixVnAQtLk4yaLoQpUWoiob6N36h3fdNaSPTVVPfRitrFO3fHXS4XXS7lUNSOX7rRmIHw-2wz4W9Olnisjp_F7fLANOKzd1XEYpc3Tmr7gn2VEQIEzp-66-yhzOPuCgObMTxk_cEifX1Uj3otgPpksHp_GOq8FeDL9dZYQjCOpfuLV4_hyU9HSUDv5FMfg5a83JLbqn3nwCeKiTltI.&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8vj5dZYOU3exZurtqeoAEOGHiJtJt0R15G-Gvu1gY4SF3XYLxe5NeW2rSYAwpQa7PODHEjcXUy8yqAfU4SKJCnt9PhjyidbA9ww9dcmZp1PIogYg3mDpvJurUPwlGVhexfg0oRh5GWBFQyRfImSn*yK7y84M2SIw9i7NxOl0QY4XmbGyU7fapM1N6Lk1klhczoSddmmGWmrA-TTV1gEh3tyCBVLXF2Byvnr9gXGXQf7FmWs5dIBZnrEsOjFWLhWqrulxRFwUqiod6DR3GozkcJ">不懂计算机,不擅长数学,照样学习自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">作为一个自然<em><!--red_beg-->语言<!--red_end--></em>处理相关狗,不是学计算机或者生物出身,却误打误撞开始了NLP的相关研究. 希望通过这个公众号和大家分享一下...</p>
    <div class="s-p" t="1437271066">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFtz0kpSjbWzERmpaAwGL3IJI" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz9rSr-DfM_xWqTTEU77jOJx9xfQ82xymJ8ISPTGZv4q-G8c9nE_SUxcdI_l8DK33Mts6V7zphAFAXtwT1sYdS0PN5DOO83xt1FefrZaNelr37d0jpZ1RpfGRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5hrZNuzTm92zeu6icjT5vKWiatJ3csib9vJKicb1FqPQRkeA/0" data-isV="0" uigs="article_account_7">自然语言处理探索</a><span class="s2"><script>document.write(timeConvert('1437271066'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-da14a0bf9b6382e1cff7478826293ac2">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9bHdB6zTQyMVXeiGuJkKhfhXJmecZp6jHK6G3UoYCv-vJlYhNkU1VzAvQqxJps7gk2ei9wsi5M9wJFopx9b7X5-IwIBfy_pUuXcVWBFj0v2gsOHdIGzbVVBUslXXXiQ4r-B4JjliRnv-k2LpQWLpTMACAJ28ED_F34jKE9oCMxu5QL0Hr9Gyd3Q..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/aOpHbzSJeGK1SbKIXIfvl0usnEHJHQIcX7rU5mzQvjaNEqEicIkPiaSRdCyaiaZ6saMDVBxECPeV3qWyrDCOTkD9Q/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9bHdB6zTQyMVXeiGuJkKhfhXJmecZp6jHK6G3UoYCv-vJlYhNkU1VzAvQqxJps7gk2ei9wsi5M9wJFopx9b7X5-IwIBfy_pUuXcVWBFj0v2gsOHdIGzbVVBUslXXXiQ4r-B4JjliRnv-k2LpQWLpTMACAJ28ED_F34jKE9oCMxu5QL0Hr9Gyd3Q..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOBQ1ku78nkoIaae8PrB1ltU4DudBT16oz*zx-6fkT5fUm0Pqy54c1QW-p6DP2Q6AEulv07*KBqauYLQvOCUzcJyDvsNCwP7ZVBmKQXKok4LzmvfaMrNE8t2BAHCODU-t1D5*6Kw5ctN*KQIzEB6bGofxBPBs9sM*8IDnM-YSd3sY=">大家研学||冯志伟:词向量及其在自然<em><!--red_beg-->语言<!--red_end--></em>处理中的应用</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">点互信息; 自然<em><!--red_beg-->语言<!--red_end--></em>处理; 神经机器翻译1.引言近年来,&ldquo;词向量&rdquo;(word vector) 在自然<em><!--red_beg-->语言<!--red_end--></em>处理( <em><!--red_beg-->natural<!--red_end--></em><em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>,NLP...</p>
    <div class="s-p" t="1562664587">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFt7tKKBwq8IqweMnrR5Z_K2Q" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdziYl7fiAbOrNORB-zq2rVGHSsfHdizPXLDDxEXLerdAObyoy3MHq3OE70icMVSzPM17AJ3lX3cP98G5799SWwTFmB9LiX_rH-zTHD0eOAFFyYvFKPp6QxnqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6BibiaQialjOzFzLK9Lo6iaChn8HvhNLib6fEiafVquyyBLhTw/0" data-isV="0" uigs="article_account_8">语言科学</a><span class="s2"><script>document.write(timeConvert('1562664587'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-c632f7ea9dfaaeeb7923a39166c61c25">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9a5oUhk6xPuGLXNDy0MdskftFJey-dOfRHGfxR-JpkHamrygXPB1f6POd9QKrrSt30egz7M6yYbckGUXDFc9mX2UlW_CNgz-TyQ8rQ3SNHv5_hp0i8Dnf-7XdcWGYwFrhy8i0dTtFdleSAlr9lQqqsLFlTn-VTdr64TD16Hn6ddPyPfCoem7FzA..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AIpX6uarG0g5x5Yn8tfstjCQ5xIbRc4iaf3d6qyGYcOZd0g0hNB9O926kffgEOGYutYXeSLriaJEwfyBsG6quglQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9a5oUhk6xPuGLXNDy0MdskftFJey-dOfRHGfxR-JpkHamrygXPB1f6POd9QKrrSt30egz7M6yYbckGUXDFc9mX2UlW_CNgz-TyQ8rQ3SNHv5_hp0i8Dnf-7XdcWGYwFrhy8i0dTtFdleSAlr9lQqqsLFlTn-VTdr64TD16Hn6ddPyPfCoem7FzA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOmeS8UdqvoRTTIFUKBtt4DuG*lqRxXyv5hUxYH-gO9Q5T7Mi5vvKtcBCC790gu68oKi7MBJMZCKbBc*A2OW4-6rJPePOQsagpID9BtXYdizLD5cXbReOvRAKmw3CcT5UYwTOQo3bjXrkbUI80PrmPbmcRGng4UjF*pkmPmhHe8Yc=">NLP研究入门之道:自然<em><!--red_beg-->语言<!--red_end--></em>处理简介</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">什么是自然<em><!--red_beg-->语言<!--red_end--></em>处理简单地说,自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,简称NLP)就是用计算机来处理、理解以及运用人类<em><!--red_beg-->语<!--red_end--></em>...</p>
    <div class="s-p" t="1559213659">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt8j17JOWrkAiumfBKLp4noM" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz3gPu7zZQiTv8WtSnXqx8XR_cDADn7D8cxglRxiS-iFaZYe6_K_9f0u-_hexwAcbI_Z1bV7HyfyATbo5CUe8dB66kve4jTQ6dCJedgJ3U5o7DD_5iWaUFEWRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6dupId3C3StpuIvpKk8B0xAibXh3oL1J3PYj6oic9pChCQ/0" data-isV="0" uigs="article_account_9">数据私房菜</a><span class="s2"><script>document.write(timeConvert('1559213659'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=2&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a><a id="sogou_page_2" href="?query=natural+language+processing&type=2&page=2&ie=utf8" uigs="page_2">2</a><span>3</span><a id="sogou_page_4" href="?query=natural+language+processing&type=2&page=4&ie=utf8" uigs="page_4">4</a><a id="sogou_page_5" href="?query=natural+language+processing&type=2&page=5&ie=utf8" uigs="page_5">5</a><a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=4&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约100条结果<!--resultbarnum:100--></div>
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
    <a target="_blank" uigs="right0_image_10" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_7HLqMzjNmVEiwuoXL0lWRXc8Pg5Cmax8hzKSfOHVuItgZMlOn5trXl2xGZue0t-OmMdqyI14Qxl0aEHSRkBhqqvQQm3T7UlaRu__j_iR-ZZInPd4O5oJ24OZCnxixtX&amp;type=2&amp;query=natural language processing"><img height="58" width="58" src="https://img04.sogoucdn.com/app/a/100520090/oIWsFt6H0vSmd7OiiNt8fAQlDxgg" onerror="this.src=&quot;//weixin.sogou.com/wechat/images/account/def56-56.png&quot;;this.onerror=null;"></a>
    </div>
    <div class="txt-box2">
    <p class="gzh-name">
    <a target="_blank" uigs="right0_name_10" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_7HLqMzjNmVEiwuoXL0lWRXc8Pg5Cmax8hzKSfOHVuItgZMlOn5trXl2xGZue0t-OmMdqyI14Qxl0aEHSRkBhqqvQQm3T7UlaRu__j_iR-ZZInPd4O5oJ24OZCnxixtX&amp;type=2&amp;query=natural language processing"><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em></a>
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
            uigs_para.exp_id = "null_20-null_21-null_22-null_23-null_24-null_25-null_26-null_27-null_28-null_29-";
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
    <!--1562763693053-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "cd50a80a-1006-4df1-bed9-ed9489589356";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693218;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693218",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "cd50a80a-1006-4df1-bed9-ed9489589356",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A52F5E36E42F2E38",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "4"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-1efbddfa5d402bb5ba806d4be8ac3d46">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9gr4c7Jrv-csz9C8uZf0-Cdn8LhdolP2ffMtxFUq6fmzPoacCFJyUL1AvHhQr9CiYsYRk1PMqY_AOboS7EiWtPzKrhmIa0G91D3eMoL4LcZrJzYsOQ_mVnzAIT0QGq1CvPlxdvI6EBG3UFLy4fjnIq2V0EwUlRsjP7qufMquZ2IgYJSSFPgfogQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/xXkqkQriaAic4DV2zFzsVcjfFscVfY2uq9wnZ3LgkUbdwg4pvksdGWtlbbUia98l17icK5D7AZSv3Onw4djrB9wgKQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9gr4c7Jrv-csz9C8uZf0-Cdn8LhdolP2ffMtxFUq6fmzPoacCFJyUL1AvHhQr9CiYsYRk1PMqY_AOboS7EiWtPzKrhmIa0G91D3eMoL4LcZrJzYsOQ_mVnzAIT0QGq1CvPlxdvI6EBG3UFLy4fjnIq2V0EwUlRsjP7qufMquZ2IgYJSSFPgfogQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAObdYufrUO**v4tk8LosDzXZiaMCEcyvW0*qvx9O5993Pgs1GGWZtJubZDsA*OguJMdlAsRcPJT1AxPLOCOoF-G1O4RHFQ6J7H*wAQTLb5iLZP4ckgtbLfDmD7Ug9V9Tthx5PsXFpKNRyRGZrXiRvDopyGJMMh31HzSvB1MXc8MHc=">广电行业的自然<em><!--red_beg-->语言<!--red_end--></em>处理</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0"><em><!--red_beg-->语言<!--red_end--></em>也是人工智能的一个重要,甚至核心部分.自然<em><!--red_beg-->语言<!--red_end--></em>处理就是实现人机的通信.NLPNLP (<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>) 是人工...</p>
    <div class="s-p" t="1562143505">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFtxmF1s9nIPYIlJhxFJEAT_A" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz1NTtIVU7TFu4wzIdgUCJChiKFlGD2VzIN3FTEVW65L42KUhFAsWxQEqnVIKund82gb_PotIEfWTcUg2U2HvKOGAtLH5o-u1u3BMpysQpJk6MitmptYkGeuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM71MqaLpQC2goVxNODwbicpibzVMoYwmsoTWh6BRD0tBfpQ/0" data-isV="0" uigs="article_account_0">四人小窝</a><span class="s2"><script>document.write(timeConvert('1562143505'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-bcb0271d1aa9b8ef66cf15451ae6252c">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU619y8bvZjrAg-PYs8EqlAAhF3XwmtWNzEfauKZeHro66MZ-YvfrbE48BSh1aBt4MpdcPxxh2EzbBeXkFsbfZdvcboB_eq7TfcxsUDSHQkBQvBFEYyPcRrkaT3y08OLTBhW0A..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AefvpgiaIPw2NBs9UmdUjVcry2o94uK5ooYPy07c5V1kicia4QTkCGPU06FuE14rGHTuNWjQe70zOibjEj3sQkl58g/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU619y8bvZjrAg-PYs8EqlAAhF3XwmtWNzEfauKZeHro66MZ-YvfrbE48BSh1aBt4MpdcPxxh2EzbBeXkFsbfZdvcboB_eq7TfcxsUDSHQkBQvBFEYyPcRrkaT3y08OLTBhW0A..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOfx8Jfwfb0qSMYPxNYhbrgeO7FUYMDOhFsE5IxVJPUWS0o4VighcWrbTwx*SUXNettRUE458f0*YpjIIwC9BsKEqVzvd1eTUj6b62kWomii8I0k-5sZBxVZR6zjE**rZ6cA6guG0UyipbUtUi5W693Numrjp0lDkOKuxXeLmkMsI=">Ruder博士答辩41页PPT,面向自然<em><!--red_beg-->语言<!--red_end--></em>处理的神经网络迁移学习</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">Sebastian Ruder博士的答辩PPT《Neural Transfer Learning for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》介绍了面向自然<em><!--red_beg-->语言<!--red_end--></em>的迁移学习的动机...</p>
    <div class="s-p" t="1551340272">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt76uwDKxyiHVKwWo3xeOGlQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzOmfPGPvs25f63z-PZUbG8HxQJWHLEey2lB_Az_B87nOJKBnIhqiDW7MGTbU99d_IxbqfApI7PH6BhddYaTtWZ7hwmGFwNQ87y_bdZbkQO_tbR99V7P4u1eO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7iathEPUfgnAWr4Hml9INphvANAFNW2LkrRd5RxBqiauzA/0" data-isV="0" uigs="article_account_1">专知</a><span class="s2"><script>document.write(timeConvert('1551340272'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-bb49ad44f4c966a8e9a045b4a8846224">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7qFqTGMZ37lJtvuGCDrlXmJBdD_bSuPFp6PJL2_RH_2Da5vO7cqznaGSsZFzv0CRPNJkQREJRAqWVLFpQGjznBayCu1nkJwWYQscSobqmHVk0O-Jbg39_xoY-UZGbO56rA..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/UicQ7HgWiaUb0gXoMRe0Mg9T1Bq7bCCPuqjGDFqDUoBE55hVXm6x2mwiaD81ia0coCMVNAjWvRAxic5Q9OqqJAOjCuA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7qFqTGMZ37lJtvuGCDrlXmJBdD_bSuPFp6PJL2_RH_2Da5vO7cqznaGSsZFzv0CRPNJkQREJRAqWVLFpQGjznBayCu1nkJwWYQscSobqmHVk0O-Jbg39_xoY-UZGbO56rA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOgeItqUApjgMEtbjB4rdbLvMChsjfl95p0wFN1tKgWWJhAvNIQhvJleNUYfwT9ltdCUeMrx*6Q0eNzy6q7CEZv9qjI6Fk7gQYhh7UwEGn*vCiXtYjVZgyIIFbbkddGpgT6wVQW0HWlKfDKBRn5r3n9Gb4nl0SUhF3m1xAcKnRetU=">【米粉王斌】NLP大牛王斌加盟小米,任自然<em><!--red_beg-->语言<!--red_end--></em>处理首席科学家</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">博士生导师王斌正式加入小米集团,任AI实验室自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,NLP)首席科学家,负责自然<em><!--red_beg-->语言<!--red_end--></em>处理基...</p>
    <div class="s-p" t="1535429225">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFt_3tpR1cD_MGm5ljX55Ax5c" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzViSEkacHRFSKCx5M6WPU9IiKMn1vwlifhlsQEmUocDHUlvTfZtFTmyhc1lIRO1PSb88B4w5eYxyCY4UtGOwNTTonJ4avsjm6jVxqWvBdRMz4ysFTJOK9RuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5Ge0ZibsJqTzd6HdTSHcydlic4TnsmpJicUrIlicD1L9ficFw/0" data-isV="1" uigs="article_account_2">新智元</a><span class="s2"><script>document.write(timeConvert('1535429225'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-613633229b862199be26c1a5c1d1e4b8">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5naUPqiK7OIqcRpKub_CIjTGmgB4Aoumin7nkzo0oFfFWVRDp7_e34bqcYuQ5YXhby5Q_DMnB2F44B1Mj93cBAjn3hNMdzwKO5Vu3Q_sh1l414qhxzF3x0GvP28temKTOwg..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSKtKjGicia6r5zb23XdJjzgso3SwbkNgKGIs3vMMemCViaq5I2SicmSxlN6TYAcXaDmcqsIyFDUUZTS0A/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5naUPqiK7OIqcRpKub_CIjTGmgB4Aoumin7nkzo0oFfFWVRDp7_e34bqcYuQ5YXhby5Q_DMnB2F44B1Mj93cBAjn3hNMdzwKO5Vu3Q_sh1l414qhxzF3x0GvP28temKTOwg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaffGF4UDvac7JhL7P1HbVIjJqWr1HA0dZVL1cy0wiwWY9UgphmfR0FRwgj0Go2N9Hpv8q3nEqD66lwgeY37326s6CVxZ9IpbxDj8TpDcwmt02Lc8gBqYaVDQcAnfAeZrSMWI2lYvDCHZwxJtt4aOMjI=">Awesome-Chinese-NLP:中文自然<em><!--red_beg-->语言<!--red_end--></em>处理相关资料</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">awesome-chinese-nlpA curated list of resources for NLP (<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>) for Chinese中文自然<em><!--red_beg-->语言<!--red_end--></em>处理相关资料图片来...</p>
    <div class="s-p" t="1550378500">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_3">AINLP</a><span class="s2"><script>document.write(timeConvert('1550378500'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-b6c9a14d2a8a80a780a81dfb32fd9569">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9LBpcqWXMiGxRBZl8qBxZKwQssPFvcBV0qc41sImeKp8gvJHOMUC0JaH5nr5vd-NLZTx5VnCOIp7YJuNkWkbxfK3d7KaqFQqG4p2a4QShoQUvNXU2KM-F0w0_rAMMTJUTh6g5gtQ-10fIZ8M298NrRM4dEaEGu9B5G5pHPSV5X32fxjh3za6jWA..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/vJe7ErxcLmhiaaH851kia8Nx7sIIXudyw7RKKrvV6Um961TTSTr7TQt2BDwV9kzEdCWaBnpVr9VqQlicDrCKqduKQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9LBpcqWXMiGxRBZl8qBxZKwQssPFvcBV0qc41sImeKp8gvJHOMUC0JaH5nr5vd-NLZTx5VnCOIp7YJuNkWkbxfK3d7KaqFQqG4p2a4QShoQUvNXU2KM-F0w0_rAMMTJUTh6g5gtQ-10fIZ8M298NrRM4dEaEGu9B5G5pHPSV5X32fxjh3za6jWA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOnAgXuYBXu1P43IkzluzZwFv6PjNO*vzZXAXGqCes7RciE2AtSVJ7z4oviG91QdzE5BPXbsSHr-BGo5VjaEa2w6C5OQ8y*DFE3k5NEyHmsfF-mri6apj8rtrestm0se0RUiTyNyc9UNsuEyaHqo5CT2UZfNPA2AeazIwzBjm118A=">一文纵览 Vision-and-<em><!--red_beg-->Language<!--red_end--></em> 领域最新研究与进展</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">vision-and-<em><!--red_beg-->language<!--red_end--></em>?我们知道 Computer Vision(计算机视觉)和<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> (自然<em><!--red_beg-->语言<!--red_end--></em>处理)一直是两个独立的...</p>
    <div class="s-p" t="1557834312">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt6jm0raXmGK-t7HSyLdSH2U" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzjaLaZfuhzA-G_zISYyAX0W2g4w3UE1SzpjDpByZ64zB_B85muWG9pC9YR1CR2ovghRCT7TLlQd7so2J4kLgVfslAFNVlZBRPhuoWGjEcRn1dR_lAeqrE7qUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4zibpuGovwxHtsNaPsk8dNIsRWSZ2adUMCjt1SrpIsVJw/0" data-isV="1" uigs="article_account_4">AI科技评论</a><span class="s2"><script>document.write(timeConvert('1557834312'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-666723603b5b96792bbb4af6ff22b00f">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nVK4TU4FSE-00I9SxXbPq06gWUF_4VIsWeRZCiprDr41lg_Stdm1VjKpbphy5Ki0BOrrU9L_xg8bOSDRIUeIBD7-w14cG8X_FAHWQK3g-q8mXMy1o4I7LegO8fIRwtipOg..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSL6ODCGY0EZUOlJZvtEadfBZGRvPKpoMM4TtGLA7YiaJcoFm4icTUDNngTjDcvf6DYibvsNNPs8dplnA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nVK4TU4FSE-00I9SxXbPq06gWUF_4VIsWeRZCiprDr41lg_Stdm1VjKpbphy5Ki0BOrrU9L_xg8bOSDRIUeIBD7-w14cG8X_FAHWQK3g-q8mXMy1o4I7LegO8fIRwtipOg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaffGF4UDvac7JhL7P1HbVIhq8TZCfHtzhDKP8Ac0zeyScZnT*3nsW4zsKx-D9vcMIopKbbtU77q081aE8tmLqnbWljPDEe-7cZqlqufq3*gz635TjDnaZ8r3k8t*TX2KsEtbyik-KYcy-ngLvhyLKhg=">CS224N 2019最全20视频分享:斯坦福大学深度学习自然<em><!--red_beg-->语言<!--red_end--></em>处理课程资源索引</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">大概率这门课程的视频官方应该分享完了:CS224n: <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> with Deep Learning Stanford / Winter 2019通过...</p>
    <div class="s-p" t="1555830763">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_5">AINLP</a><span class="s2"><script>document.write(timeConvert('1555830763'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-118d16e909d94ccbf6a09b06f490cc4f">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9m3KijG5S6SxzyfpCIT3czGOakiDtDp04ryZSINJMpt0t1vK3A8jn7l05naLpX0WKNSdUJzW4PB6Tm6fC2fq_j-D7H1yftjdlMQBx4m6yn0hpRj-KJRduHH4xJkoY9KK-L0aDmCk-6Nj4enYjYDgNnhLeQiW6GwmENgLeB59VzdejotuuiAmOIg..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/icYvar50EZDzdH7EgY3uNualzuVRjSzaoV1k7Dhrrwj2nMg0h4knqVFkPmZg3iciaXTfwx4pSrQ2FLPoKMZ4Eq9Tw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9m3KijG5S6SxzyfpCIT3czGOakiDtDp04ryZSINJMpt0t1vK3A8jn7l05naLpX0WKNSdUJzW4PB6Tm6fC2fq_j-D7H1yftjdlMQBx4m6yn0hpRj-KJRduHH4xJkoY9KK-L0aDmCk-6Nj4enYjYDgNnhLeQiW6GwmENgLeB59VzdejotuuiAmOIg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOgXgFOwNOEMYVs4lugeuOP7SDNoRr*Hk*OBIFS7rVll9g17zg-44C0XlzlBZGIC-9xNmFNK1TB1lOZVqibsVjCDNWYN0M3a406pIVYEDhww8LLs-hs2IZ7LL*mSLCBeL1tb2rbbGM0ReYzo5TpHgSSRbX2b54g3Z6gvk0Gt4vchw=">NLP_03_<em><!--red_beg-->Language<!--red_end--></em> Model</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6"><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> - 003按语:本文是学习笔记,重点是<em><!--red_beg-->语言<!--red_end--></em>模型.提示:出现英文、日文,熟悉专业用词,用于papers解...</p>
    <div class="s-p" t="1557765312">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFtzalONyQaPIJMwrYg1fUw_E" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzwQrg3mLpQomsK4FhwyE09s73XY4PigMHZjupT1Tg_FRVAZHXOrY_MC_Rjln3r4qkoWKn4ow6C8vzUl5n7g7ZyEC9c_ANFPOsorBmKZVOGh5NGC6LhK3HJWRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM65Vk1A0BfGIU6eOfQRJR9Cgoib91dmVSscFlefj98Z0icA/0" data-isV="0" uigs="article_account_6">勉強中</a><span class="s2"><script>document.write(timeConvert('1557765312'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-cb8f4b52e0906a11beb6c9109e012dad">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd93maIjd_HEROCyTh_61OofWjL1e05Z4VEM5F4wAJg0lnGq-Ys2GHSNEOPaDaBKdto6qdVr5Y7tumYAp7vgeUO1z2jFYlJXySXXa98_wUb72j3bdVSk6z32WDoVb20sbiPY7_1H9wRgB_1c30Jx_6Iwx2V2mcA_c1SbsOKNB7CPloNGbbB75bUeA..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/LibQHNHIKUnR81RdYrrUpypgvW7ianAeKfrDYl0icOpZ7w6AXAFh0P7fIAUaNiaic9wxg7t7vx7e9n4W4EAGMavp5xg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd93maIjd_HEROCyTh_61OofWjL1e05Z4VEM5F4wAJg0lnGq-Ys2GHSNEOPaDaBKdto6qdVr5Y7tumYAp7vgeUO1z2jFYlJXySXXa98_wUb72j3bdVSk6z32WDoVb20sbiPY7_1H9wRgB_1c30Jx_6Iwx2V2mcA_c1SbsOKNB7CPloNGbbB75bUeA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOXaDcWn53ve1pKQoawioe9nOizWctKcT2JoNMNbUBsPhf6mJ8pktxSXEf6kXawCuqET7AxBc7YhOJl99s5RbP0WHkiL2Oxfhzob3Rool-9d-flBqquQxvSmTFW4gGcVPyC04NGuIuaR-7zHnSUVpkJCDNTIKg77x9OjIms-DV40E=">讲座预告 | 佛罗里达大学教授带来讲座:用于深度自然<em><!--red_beg-->语言<!--red_end--></em>处理建模的张量乘积生成网络</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">of Hong Kong, Shenzhen02AbstractIn this talk, I present a new approach to the design of deep networks for <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>...</p>
    <div class="s-p" t="1560919448">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt_vDA6na-sgaqlFrlmyitiU" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzklQ3aWFG_7pm9bBJL20KTglkC6HZ_kTWINnsu22cEC9qkfAVn6qtVSbkRMCEvwkefx3oeAOPfVoD09lFBsrxObAbGFC569IQwbtUwe_vVMdKBjaCYRjR8KUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4iauzGsrslpY8PVt9sBicTCjjavscx8PuR9u3CgJicaKndw/0" data-isV="1" uigs="article_account_7">香港中文大学深圳SSE</a><span class="s2"><script>document.write(timeConvert('1560919448'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-5d218bcf4cf58f37538d8c5a6865c72a">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9Q9RrlEE7Js0Bw_gE0pFfeow0-F4bWWMHFMzjPUmUT8ok3N1EYCItH7GZCUC3uDNJ2f0povkD-576R_nLhJPdDxYmAIa5H627RZf5Wnh-NdrsGEGOOiMGv7-di7qBfd1JzXwsV5J3k76EvQg3aHi1fbqsIqDMBs9556n7IMuFDN9S6t2rFt2rnA..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/OhiaiaTpArm8UBB05WNfYib37n9zvCs6VTlGHEpXfTRwMibqqlembQYZTzp10ZjN1QekpZAgD4vmM2vEqkxibZud5rQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9Q9RrlEE7Js0Bw_gE0pFfeow0-F4bWWMHFMzjPUmUT8ok3N1EYCItH7GZCUC3uDNJ2f0povkD-576R_nLhJPdDxYmAIa5H627RZf5Wnh-NdrsGEGOOiMGv7-di7qBfd1JzXwsV5J3k76EvQg3aHi1fbqsIqDMBs9556n7IMuFDN9S6t2rFt2rnA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO-KdOi7QxV-1GsY935BHhV1IOsugMXIW1lZmf32wyim6NdH8r7evaW41DFPGJc1rjU9j6V*7DLF3AiFF55JwAIEqUfOJ5l1MXfOHtTwtcSQHaVwi4R4l8VAMUGjDCE4PGIHsQykj0Y5J2OPnc8PwZx*WHRcO7-T8OCkq4KFU0**c=">学职 |【Austin AI Tech Meetup】听大牛讲NLP自然<em><!--red_beg-->语言<!--red_end--></em>处理的应用!</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">We will focus on <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> technology this month and have two speakers to share the latest work on AI and practical ...</p>
    <div class="s-p" t="1560307719">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFt7v4sp8hHHr-6Agx1DjMDx4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzmI23ygdd-gukTxk-BMN7ZS_lR581TMvfkNXG6RtPCToo78Ab2JL101CWyapJzMpUQy8C2dm__rOrabNRNCPkMQe9QVX9MI-rIEyESzOUkfWNeV3CA4xd-mRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6wCeFgOC5apU2sIt2deqAxeLJicZR30z8krgcHvLr8xYA/0" data-isV="1" uigs="article_account_8">UTAustinCSSA</a><span class="s2"><script>document.write(timeConvert('1560307719'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-51a880395c685ff78b9798a35d0a984f">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9Q9RrlEE7Js0Bw_gE0pFfeow0-F4bWWMHFMzjPUmUT8ok3N1EYCItH-_-SqyMcZtpldOchql67ooXghWYKQekh2MbX4dEztIyzQBQA4M-ZVC2nIDyUnxbRR_0m9ICy7R00pWeYeYf2vxBjGjDlLhdP3JpVO3O5q_TNaYbfO6r497FcvUoAZZH7Q..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/OhiaiaTpArm8UBB05WNfYib37n9zvCs6VTlGHEpXfTRwMibqqlembQYZTzp10ZjN1QekpZAgD4vmM2vEqkxibZud5rQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9Q9RrlEE7Js0Bw_gE0pFfeow0-F4bWWMHFMzjPUmUT8ok3N1EYCItH-_-SqyMcZtpldOchql67ooXghWYKQekh2MbX4dEztIyzQBQA4M-ZVC2nIDyUnxbRR_0m9ICy7R00pWeYeYf2vxBjGjDlLhdP3JpVO3O5q_TNaYbfO6r497FcvUoAZZH7Q..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO-KdOi7QxV-1GsY935BHhV1IOsugMXIW1lZmf32wyim5Jk5C2*xEqAB3rzzE7yYL6zT0a4j3LS9wbgrnlgM2Vc4EK07jtlm7EHYFQJsGOPS0NOlSDSwTL6ZCZDmhdZA5H2VJPdYGoSvz4WK5KEBR5mY8xw7ThhQTcbWvqQRwjlwk=">学职 |【Austin AI Tech Meetup】NLP自然<em><!--red_beg-->语言<!--red_end--></em>处理应用的讲座就在明天!</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">We will focus on <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> technology this month and have two speakers to share the latest work on AI and practical ...</p>
    <div class="s-p" t="1560826616">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt7v4sp8hHHr-6Agx1DjMDx4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzmI23ygdd-gukTxk-BMN7ZS_lR581TMvfkNXG6RtPCToo78Ab2JL101CWyapJzMpUQy8C2dm__rOrabNRNCPkMQe9QVX9MI-rIEyESzOUkfWNeV3CA4xd-mRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6wCeFgOC5apU2sIt2deqAxeLJicZR30z8krgcHvLr8xYA/0" data-isV="1" uigs="article_account_9">UTAustinCSSA</a><span class="s2"><script>document.write(timeConvert('1560826616'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=3&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a><a id="sogou_page_2" href="?query=natural+language+processing&type=2&page=2&ie=utf8" uigs="page_2">2</a><a id="sogou_page_3" href="?query=natural+language+processing&type=2&page=3&ie=utf8" uigs="page_3">3</a><span>4</span><a id="sogou_page_5" href="?query=natural+language+processing&type=2&page=5&ie=utf8" uigs="page_5">5</a><a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=5&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约100条结果<!--resultbarnum:100--></div>
    </div>
        
    </div>
    
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "null_30-null_31-null_32-null_33-null_34-null_35-null_36-null_37-null_38-null_39-";
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
    <!--1562763693218-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "5e9f8781-a26a-4187-a829-bafb0131294f";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693309;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693310",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "5e9f8781-a26a-4187-a829-bafb0131294f",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A52E0700E42F2EF8",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "5"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-28a16b9a4962c8b01283f243f2fc80e8">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9LDI5etyodDEow0Koy49eY1GEn7kJJqbVa5Usy0WglEywk5B4upTM0ScZiZs_Euf8u1kgUx2X2hTqgG4nLuWgf2CVg5vcUf_uOrJA7yjAlIDVqlHhmErMye7kvHfniJYyRWmcsTqGzc60yHz-I7f_CjXZcaHkT2YbImToGux2cAns46dn8Efgxg..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/u7sgcDPmc6f0IPngiaOoShBUvBSVMFiaYTMZiaT1F8Y3yiatGTBf3KtoXMEhhqbBh3SDmqibt67ds9ibWgSVa6kLwrfg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9LDI5etyodDEow0Koy49eY1GEn7kJJqbVa5Usy0WglEywk5B4upTM0ScZiZs_Euf8u1kgUx2X2hTqgG4nLuWgf2CVg5vcUf_uOrJA7yjAlIDVqlHhmErMye7kvHfniJYyRWmcsTqGzc60yHz-I7f_CjXZcaHkT2YbImToGux2cAns46dn8Efgxg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOY3ZUl7De3xFHqvQB*q3a098lqx1MX01rC2nt49x1b85xgDlM64lCO0ce4gPuT4DB*kogeNhbZKPOnzInPPRlRsxERTBX5SJpWEvQ9YbayrkS6NDtoxiDvGwPbitzTscXif*XselISK4EvN6nxPiydQ8BILQTWWlWV9cbSVgwJFU=">【德勤智慧审计】第六期:智慧审计的七种武器之自然<em><!--red_beg-->语言<!--red_end--></em>处理 (NLP)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">1. 形态<em><!--red_beg-->语言<!--red_end--></em>是表达人的想法以及人与人之间交流的工具,自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,NLP)使计算机拥有处理人类...</p>
    <div class="s-p" t="1562242395">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFtyosJpzK3rCQvW1_ql3Bzwc" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzCtSDaLhjDD_OzsSidEEbRuXp1MOWJ-iggXcD-pfhlO9IeVuisOK1BFk_Z2231nEhYBgZ9zJUtqtnG30CU3m6OAtywCSEp5w-wap2v0RJB24lSzfUbdtJyOO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6kF8oIrshCRXjtIgOIDX5kISuu27hTEQKJOx7ZlR174w/0" data-isV="1" uigs="article_account_0">风控在线</a><span class="s2"><script>document.write(timeConvert('1562242395'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-e1630921e43651b842b0085e6d4acb9a">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9SE6OTVyEn7fW0NNg-NWgKQLjFXKwQC0Toog9xtQ4QfEUiXKsGSRsptBvznWUsce14Isr6NtjeuNrAbnkfl8qq1RqofARaA9dodnlMWfJQpVYaCfSKgMcjxKcoVOV9fiToBBkC_a2sFQReJbZvdnZQNk4D0Czx7Q_VV66nDExeVg5eBgmN3LoYQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/n19EsPmC0icbGlcEoyPFPKKiaZnqLDuVbPAQrD8yeseBIaLUg50fib3pVWu5GJGs2407v3t740pFam5whBaHBCwCA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9SE6OTVyEn7fW0NNg-NWgKQLjFXKwQC0Toog9xtQ4QfEUiXKsGSRsptBvznWUsce14Isr6NtjeuNrAbnkfl8qq1RqofARaA9dodnlMWfJQpVYaCfSKgMcjxKcoVOV9fiToBBkC_a2sFQReJbZvdnZQNk4D0Czx7Q_VV66nDExeVg5eBgmN3LoYQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOJT2A3MIJilVgFujqSa5afeepDOsUIgFThu4iZAX0NRfnf*bdLLdjL6S3aO2CPxsIj7ofz0TiN**MHr873evMNHFc8PcLABHOE7BGHfvU*2QyOkjXOiSzvpYvl6cOZ3cCZcWKWZau*ys7w6Va7fSh7*wiqX30x7mcjTy6O8p*bB8=">Chilean opened a <em><!--red_beg-->language<!--red_end--></em> school in his 2nd year in Nansha</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">a <em><!--red_beg-->language<!--red_end--></em> training institution in Nansha for more than two years. ... with a complete lack of familiarity with the <em><!--red_beg-->processing<!--red_end--></em> process of ...</p>
    <div class="s-p" t="1558432821">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt4MKqTgLzhajaG3zArQS-dA" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzxm2nPQNLZx4dAnWE7EEb49a-RQbllhPA8Y7mAUyPAShBuMlR6KQGcqleDp1G_DyuUi60Tq8KZNQmKUdJYmJ0hgeqdliNeRTT5q-pboNZf28JG8Emc1_6ZaUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5enPbIXpg8ch05WDZlic6r6zNrzR6jYsL4ibS7PqHXxk5w/0" data-isV="1" uigs="article_account_1">南沙人才</a><span class="s2"><script>document.write(timeConvert('1558432821'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-dd0e180f7ca0adf9cee260c208b8c8af">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9szbivErKQQMJb2ENwiK9A7agyO3JuKMmEo7gE_Gdf6EhwEiluXouwnMxvzBY5XGXxLJWKgXSQrZ1vhBfQONFXynj2xFBItspdMrtXz0nzPCPmUoErjIwrSTmIGRj6DvfdYzwBoO4vliQerovy0g-GXymmHkp__dcBBbOeuxIHKLP28temKTOwg..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/KmXPKA19gWibd4TfHEjYapk3gLibSLkrZJJWQoeRJicPMTyETb5HFITwXEuTFptbrSw8QuRTlrXhATN8BKZYqHEBw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9szbivErKQQMJb2ENwiK9A7agyO3JuKMmEo7gE_Gdf6EhwEiluXouwnMxvzBY5XGXxLJWKgXSQrZ1vhBfQONFXynj2xFBItspdMrtXz0nzPCPmUoErjIwrSTmIGRj6DvfdYzwBoO4vliQerovy0g-GXymmHkp__dcBBbOeuxIHKLP28temKTOwg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO12VXWc5T7So3IHmcjQxEYDDLPVe-Rp6L8LPgvOQI9nuMXFCCYPqhBBgB7N-RX0mcZ0EfobrMaTXbJyEAXpOFuwMvzXwd7Ueq4uHfBcPQRXNWJqyky39KnTlM86AcAddtQScKpPT5Tp3t11rvOHOy8u0FwqeJ8fmJtZtfPagTlH4=">现有模型还「不懂」自然<em><!--red_beg-->语言<!--red_end--></em>:20多位研究者谈NLP四大开放性问题</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">Stephan Gouws 和斯泰伦博斯大学讲师 Herman Kamper 组织了自然<em><!--red_beg-->语言<!--red_end--></em>处理前沿会议(Frontiers of <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> ...</p>
    <div class="s-p" t="1548131817">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFtyH4wzDYSYFwlcMk8znCtfw" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzRGLZIEUzJX_qOWODnETUR8bTIFw0JvUdInDmj3SPFza0m3lasfxChdRNDh94disQotE5uOuK0PKpJPp9VfuAj6z3iIgUW7UQfiA4iaH8rDrWGWpmld6JGqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM75UiawQgcdqOcmtYS7Jibug9J7dskxkNicGiadtdKl7mLyiaw/0" data-isV="1" uigs="article_account_2">机器之心</a><span class="s2"><script>document.write(timeConvert('1548131817'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-91817e1a543471dffaf221f4bf4f805b">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9ogEouDJYk3S_Z0v_pCyYGicrwmMI8gzNrDQoiqc-d91XRwbeiCKWGTkyhQgppaBoKtb_SzQUmIgyhva5woinexiqAZ94sBVkK6dnbUq-t1-56zhsc5W2ACXKtyJXx4gDDOwJgO7wdQzZn6K57ltHLUZm0QChaazhFlLemBtX1vthWLv6O878UA..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><i></i><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/PLSAhuElFxmoUKFSCEw5v3YoRLaEFjK8hLzysFht1KxORPEicTp4jVibWqp6OMoTiczCasicdSmWD1LEE1iaHvHhflg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9ogEouDJYk3S_Z0v_pCyYGicrwmMI8gzNrDQoiqc-d91XRwbeiCKWGTkyhQgppaBoKtb_SzQUmIgyhva5woinexiqAZ94sBVkK6dnbUq-t1-56zhsc5W2ACXKtyJXx4gDDOwJgO7wdQzZn6K57ltHLUZm0QChaazhFlLemBtX1vthWLv6O878UA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOCKpFefVIJdH6D7HuPyme7a7vdcQFXz-ejxOfIjBIQ6qM7XiduwwD5unhbTesY*M82ihKz5gdm2v8nI5M4h2hjSfyXeu0uuf2CBEQt*LG4hlHGpschyLHwMHhTPd*IZvy8hHneVCYiOyKx71*pL4KuMCEJ0Ih*Sh*fMUKUYoma04=">中科院张家俊:面向自然<em><!--red_beg-->语言<!--red_end--></em>生成的同步双向推断模型(附视频)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">领域中的一点最新进展,面向自然<em><!--red_beg-->语言<!--red_end--></em>生成的同步双向推断模型.张老师将自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>, NLP) 的任...</p>
    <div class="s-p" t="1551246530">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFt98MxFEplSseNeqq-C3iyik" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzrRVFbjfhspK_sfk1hJBAr917QvyvssZzpIBGSs93JwrVMFwN7u6dvay12njYY1Czf4QZFtYjbzTlj04OVVFoO7YIIc4POtgOACVBZiF9q30Vx3hX9S8Q9-O00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6S4LgR8tZVEJcgLu6S1jmmicDwgrpEPa4iaQBJGY8sKyxQ/0" data-isV="1" uigs="article_account_3">读芯术</a><span class="s2"><script>document.write(timeConvert('1551246530'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-c3343d434ecbdc572a7fee6d56ed5092">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9rN_qf8r0tAAml6i959BRIF0cc3lVjBESUs1aSGmUzWvpYa_Pxd7Z16YBrOTIiT239zpErllyNz_3O5xJCs_Lxx8Wjs2JoavgiisY_L21q4Dx7c9yuTB7qYOkrnG8AEcYBi2qvRVH0_zX_Nz0HTyWOavBdoLgr_hR7FVUP9RO_YQ89kyxDwoXvg..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/2ocvRUl68dh5YOj6icVmibNyGsvF4MqsvHWuxAxpibkKN8brM9WD6nO0qTKibzEgUl1dGbsh5H1TGqWlIgmGh4MHkQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9rN_qf8r0tAAml6i959BRIF0cc3lVjBESUs1aSGmUzWvpYa_Pxd7Z16YBrOTIiT239zpErllyNz_3O5xJCs_Lxx8Wjs2JoavgiisY_L21q4Dx7c9yuTB7qYOkrnG8AEcYBi2qvRVH0_zX_Nz0HTyWOavBdoLgr_hR7FVUP9RO_YQ89kyxDwoXvg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOGVbHFVlYbGk6R**-gUZpLv*TRkG9HzALxTYVt-k98kdt*a-ZzUn8CI-ByQT-5QwjbFMx50KnZPryvxLAfp*vrvIPNnMQo6pkc3RwX5qTHGk6rpL6BVcs5gttG-P5gPdBuUFDQG9Vx46BjrWtC0D7PboLYJXQhfES36vKRKiPwMs=">国际瞭望|从大规模的自然<em><!--red_beg-->语言<!--red_end--></em>中释放文化数字足迹</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">for Geographic Lexical Variation.&rdquo; InProceedings of the 2010 Conference on Empirical Methods in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em><em><!--red_beg-->Processing<!--red_end--></em>. ...</p>
    <div class="s-p" t="1558886459">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt8A7cYfk4IwUBBIuhDJCaVU" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzFUTZH50LkJ4lxxMocNzDThICYKcsBt0MKP7usa6ZeLrhBipJpEJUwzBfcTg26szxoKcGM1f5Bhu4EGSxWLf2LHOESTezKSRzC9MKmk6fd7QyxnOHYLha9mRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7CfdRvDkzoRq2J0TxVmYYKVuRgiayPpia8OJ7cHqENibztQ/0" data-isV="1" uigs="article_account_4">慧天地</a><span class="s2"><script>document.write(timeConvert('1558886459'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-faa74fe8320f00523c9970701146e554">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd93wg_zpvoeCs_jOlq88N3ovu-RoZb3NPp5LiORiEl-h-eAZFXK280ekKajux9ClcCGHfmBn2sTjz3S8ySC9JFF7eChlHIdeG8aj3RcJgXxoUwGwXOAutw0Skc8BpTIuHYVcAle4A_2Sg_aFt27v8fVM5yNoWFsa6dmPmTHKt8u4nm0CtGSSkZQQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/qibibGYHXs208knN327Dn9icpnrnyUAeL87fEESF5piafxhlwueHibLHaxr6GYKOOIHQCVzNibaHts4n0pu0QLz6tpGw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd93wg_zpvoeCs_jOlq88N3ovu-RoZb3NPp5LiORiEl-h-eAZFXK280ekKajux9ClcCGHfmBn2sTjz3S8ySC9JFF7eChlHIdeG8aj3RcJgXxoUwGwXOAutw0Skc8BpTIuHYVcAle4A_2Sg_aFt27v8fVM5yNoWFsa6dmPmTHKt8u4nm0CtGSSkZQQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOeeHYHA*YIeAmk2Rr2SDBkVVPfly2-pkvw*wvykq8CXisjy*3Bn-vVjOByRKs072*WBOV63uDploa2X585jk1OjfcM8ROLt887OCFMsqwHitcfZnLAV5jxE2BQBo*9lW1rpcs62U04tONLh6yH5RK7JS90gMJHnWg80aj9z6wAvE=">广州中小学将试点人工智能课,AI的有关表达你都知道吗?丨今日热词打卡</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">computing知识工程 knowledge engineering自动语音识别 automatic speech recognition自然<em><!--red_beg-->语言<!--red_end--></em>处理 <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>聊天...</p>
    <div class="s-p" t="1562590815">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt4DOXAWzhVkH9wTb0wpXcas" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzZif49noV4qbaTTaCSiHawVAjdzbF2ytH6HzQNb8TMFOzGKLHY882Bqf46b3shgGO8iagcvoHlpVT_fNVnwvTlcRkfrAtZGrvk46rZh6bEQi5qqaM78Z5xOO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4FGWW11rCUuftSIHRlLP6YtmFLOf2SFneP5rvozVDvUw/0" data-isV="1" uigs="article_account_5">中国日报双语新闻</a><span class="s2"><script>document.write(timeConvert('1562590815'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-da0530bb209c361375d99b609217fc88">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9G9s-BLCVGzBQU75WKfX7iOjIRjALvcFC1cT2zoAdNLxzaMv6NMtjrjFD0OFzzJDz8oOOXinaJLHb4tOtBEs2lCfKHJiuDtyAOJWDeFVzzZvKPMXMv3wdYFLnBARdLt0RP4CHdFLKoSbe1xcsrcnwpKoM4FkhbyNcTTyXFWBzNHVr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/icZklJrRfHgCiaicHicXcMbyRZ4cBs9Smc170hkBNHyJGbRDIicbVBCsDXvqv9XFOuqiaXcKNBXsDtGjccStyqwTuibuw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9G9s-BLCVGzBQU75WKfX7iOjIRjALvcFC1cT2zoAdNLxzaMv6NMtjrjFD0OFzzJDz8oOOXinaJLHb4tOtBEs2lCfKHJiuDtyAOJWDeFVzzZvKPMXMv3wdYFLnBARdLt0RP4CHdFLKoSbe1xcsrcnwpKoM4FkhbyNcTTyXFWBzNHVr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO8Nyec-JBLyNIqfj*D9mnLsAeRdoDQrGtm*O0aqK3GAOZ9kEjktW99JeSTrsPztTONljC72RtFvpgtiZZGOo9xfsBjCWtVjZVZVTaWHZMWt*8Xe5bpzdbmb2EfKV9Gp8FK8fVZKCnIimrADEL0gz0l0bLbUBp-tsX48l27YR8WnY=">1.2秒,营造家的感觉</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">这就引出了NLP(自然<em><!--red_beg-->语言<!--red_end--></em>处理)概念.NLP意为自然<em><!--red_beg-->语言<!--red_end--></em>处理(英语:<em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>,缩写作 NLP),是人工智能和...</p>
    <div class="s-p" t="1535443251">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFt86MuAacbPGA3TM1glwaTp4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzHOeFEUL3cwTdl0rTkxlzQKgWsqEAQYjCdSByXAR60Cwi-bGoZRYmKYSLcTIRGKvcJATmMl7vK_EgkLwY5CgHS7HJQyf3AV4tQkU3GOO5Pb7nCEZMaVCJ5KUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7e5erCDdwwlWzic4PAYLblRDYNOPY2jApxdeg6v1TcaAA/0" data-isV="1" uigs="article_account_6">果壳网</a><span class="s2"><script>document.write(timeConvert('1535443251'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-d17ef333024152c4bd2e5e3e26244b8c">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9OhzmQtaBJzzEPn-cwZrjLahnV02v0_I5LdbfW0WIWbiWvbjwnsTxVuRfpcGJygIcdjpHd-hcP5pHXZMKsLVvmGJSR3JzHqrHniV_H0pjNvF9_S0XRQx3w-DtOsYGJJ66RBZvs2LjFqVIBMKBdHnbgT99Ll9CV9wIU-4NyNK7vm6fxjh3za6jWA..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/vI9nYe94fsExCMoiaZXxPKDDzQOWlsjy5scA1EHQicvoVgcfb3Sy4iaiclIWyeWGYpwvhJ6QRxmsgcunAZNn6qeBOQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9OhzmQtaBJzzEPn-cwZrjLahnV02v0_I5LdbfW0WIWbiWvbjwnsTxVuRfpcGJygIcdjpHd-hcP5pHXZMKsLVvmGJSR3JzHqrHniV_H0pjNvF9_S0XRQx3w-DtOsYGJJ66RBZvs2LjFqVIBMKBdHnbgT99Ll9CV9wIU-4NyNK7vm6fxjh3za6jWA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOV6jIx1FFkSE-GyUfwsTxxezsgTRUDQ2Bx9ODMVZdWYaAM2vU4tgBOWK7gNUEddzp-4Bb3b1Z6SMFFcjQwlCXd9a9ZcCeD*bylz1PQ-9GIymX8YI0LlSsCW5a4Pvok*EnJZV3iFtRuo0XHPClHz9RwoD1ZWfVNJ7cD2NRfhcomJo=">完备的 AI 学习路线,最详细的资源整理(建议收藏)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">CV:https://paperswithcode.com/area/computer-visionNLP:https://paperswithcode.com/area/<em><!--red_beg-->natural<!--red_end--></em>-<em><!--red_beg-->language<!--red_end--></em>-<em><!--red_beg-->processing<!--red_end--></em>Papers with Code...</p>
    <div class="s-p" t="1557839741">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt7iH4VfITufiVW8QI_7FY04" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzqjPVOnQyTvckghKi3Yw2dNoUnpJ0ljS9sE6ch0jG7140MtEjSXMh4VZPkQKCPy1GJrygCt91zOzU0_YOnsm1QmIh9TDz5QA-7bKq3Bvq01FtAGDyZ9id02RTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5V0NNa8X3iaficvNDP6ozlalYvibiaeyIicNaWStDibBOgh2ow/0" data-isV="0" uigs="article_account_7">大数据</a><span class="s2"><script>document.write(timeConvert('1557839741'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-204ed619e45334a2a7739d0574d33309">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_7fQGjTyIL-1NE2rdpSHNT_PqMYppWWo_gqRlKfmDQA6nFj5HwsoxtWlUXKq4zYKwT6g0liHSmNj3QM5ePVU1Ab9i5GjvK7zQ1VReYHw3_SCCch9Wj49yahlrYrcMCeq1hYWUwvmoxnIVH-Tp230DqR1Zn93o1HxQ1JK08lF2b0SYTqT4eyLmA..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/wc7YNPm3YxV5R1OgaMN2Ngf890VY3Ukr7Ed2kxlckicHZP5QtvPOf1rZNGxF7obCR7ibhWVFAku9MJib7HoVndm0A/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_7fQGjTyIL-1NE2rdpSHNT_PqMYppWWo_gqRlKfmDQA6nFj5HwsoxtWlUXKq4zYKwT6g0liHSmNj3QM5ePVU1Ab9i5GjvK7zQ1VReYHw3_SCCch9Wj49yahlrYrcMCeq1hYWUwvmoxnIVH-Tp230DqR1Zn93o1HxQ1JK08lF2b0SYTqT4eyLmA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOPIeYvRrU8tOjcQw5HVzO0mr19H1PpRmTGiPmvE8xEeCDC6fV1E6WIJt8NUtYZzCscSjXlSxjjBCWTjz-mfru*FKoI*DUzjL3f7zZisUvZnkgHnqsrLbJNy*5Gid*PGiWFHXKfhMnapRhgQmM3fxfRigdi7rf*dfllwXuMjih4hg=">超级大汇总!200多个最好的机器学习、NLP和Python教程</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">in Deep Neural Networks(sebastianruder.com)http://sebastianruder.com/multi-task/index.html自然<em><!--red_beg-->语言<!--red_end--></em>处理<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>...</p>
    <div class="s-p" t="1537761724">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFt58NVJTkYWvPtICKgg8ka60" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzf7q-LFYKNmAkybERv2CNLE2OnEU4l-_vT6xHI0zQ6IKCKuVey7IE3VeEtijCirP7kFqwXqB53Pa3Tc2dOPv3QalnFw5igmO6M2YHelytzGC7U6eEQ8GXSm4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM46WJlQ8GYRWPhThl25rSKJEYBm408fnEkYS9DUkiaSxGg/0" data-isV="1" uigs="article_account_8">大数据文摘</a><span class="s2"><script>document.write(timeConvert('1537761724'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-7a1bf002c7c14c86713ee6749422c961">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_7fQGjTyIL-1NE2rdpSHNT_PqMYppWWo_gqRlKfmDQA6nFj5HwsoxrUu7Z3noJfB0_RsrO1haXZi8skIT9X0g1aJ_9WBb2WS3r8x12Z1uzc9cNdSSF7tqPn0zWZRBXjJi_MO7sKw3_u-JHQ_dVvA7dfvQqCeqhyKMJo4UjfVht86Ebq8fk9diw..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/wc7YNPm3YxXpD5rof1CcNcDeh4wttfjBv7qVIdlEx1bG0tSOx9lEqvrZpj8AoYzkHb2jw2s2icSXz447jElXayQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_7fQGjTyIL-1NE2rdpSHNT_PqMYppWWo_gqRlKfmDQA6nFj5HwsoxrUu7Z3noJfB0_RsrO1haXZi8skIT9X0g1aJ_9WBb2WS3r8x12Z1uzc9cNdSSF7tqPn0zWZRBXjJi_MO7sKw3_u-JHQ_dVvA7dfvQqCeqhyKMJo4UjfVht86Ebq8fk9diw..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOPIeYvRrU8tOjcQw5HVzO0jZna7cz7WdJnWEsJrS8eKpQBOB9Todpn2SRMCpVdodQGWbugkCfKVwzFZanPyDnetX9XCOs4M6rVmUHG3c0-tE*6k*RvKoX*0VNeAjKIz*qpapnQgVZJFGv7X8VRikiC*wv3yqmsjXtdjb3zahRVLY=">一文打尽人工智能和机器学习网络资源,反正我已经收藏了!</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">大数据文摘经授权翻译http://study.163.com/course/introduction/1003223001.htmStanford CS224n &mdash; <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> ...</p>
    <div class="s-p" t="1519985733">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt58NVJTkYWvPtICKgg8ka60" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzf7q-LFYKNmAkybERv2CNLE2OnEU4l-_vT6xHI0zQ6IKCKuVey7IE3VeEtijCirP7kFqwXqB53Pa3Tc2dOPv3QalnFw5igmO6M2YHelytzGC7U6eEQ8GXSm4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM46WJlQ8GYRWPhThl25rSKJEYBm408fnEkYS9DUkiaSxGg/0" data-isV="1" uigs="article_account_9">大数据文摘</a><span class="s2"><script>document.write(timeConvert('1519985733'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=4&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a><a id="sogou_page_2" href="?query=natural+language+processing&type=2&page=2&ie=utf8" uigs="page_2">2</a><a id="sogou_page_3" href="?query=natural+language+processing&type=2&page=3&ie=utf8" uigs="page_3">3</a><a id="sogou_page_4" href="?query=natural+language+processing&type=2&page=4&ie=utf8" uigs="page_4">4</a><span>5</span><a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=6&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约100条结果<!--resultbarnum:100--></div>
    </div>
        
    </div>
    
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "null_40-null_41-null_42-null_43-null_44-null_45-null_46-null_47-null_48-null_49-";
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
    <!--1562763693309-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "269bb459-4772-4902-b1a9-0369d4c983e2";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693350;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693350",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "269bb459-4772-4902-b1a9-0369d4c983e2",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A52CA2C7E42F2E18",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "6"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-457c05eebf6dbe03f6c0aadbaf7a1ed3">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9KxkLcoo1mNffJKVtP-J2bHmvodHGeurR86Mb5jjWh2czqeEWLS77QYF-OGcr0H2AeDD9cUMksBcOM9Qh2w8WgnXR9ASJNDuROSx_grBaAkfsNWQz8XnfraAjnX1wRHxLvN6WMVEr79DQF43uq79HzfJ_kEOXu9ngUEGOMgiOk3lFH6In5Ei3zg..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/Z6bicxIx5naLzV0Yvr8FLNlTFmSfcAO1AM1brW9fMhoX40moY2EOsBlBU6nPYq8iaMhKj3wo1NMgVpAXrHU2Xdcg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9KxkLcoo1mNffJKVtP-J2bHmvodHGeurR86Mb5jjWh2czqeEWLS77QYF-OGcr0H2AeDD9cUMksBcOM9Qh2w8WgnXR9ASJNDuROSx_grBaAkfsNWQz8XnfraAjnX1wRHxLvN6WMVEr79DQF43uq79HzfJ_kEOXu9ngUEGOMgiOk3lFH6In5Ei3zg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOuh6DOda6rDnGk36sGhtiXDh2Ufa90ZEbIuSCfFIAflXkLHlYSuWSLJaHDlfZAs-si62WfmcW4xhTliHGcSzz2RvcoJH9n4CuqzieU2AmWy2VkPEb5sGkwQPdZGuoI4FLCOvyzrJw2do8t5*CgTStPrWdpfGdx1x-8yPnjxXUO-I=">首次公开!深度学习在知识图谱构建中的应用</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">learning for relation extraction. In Proceedings of the 2012 Joint Conference on Empirical Methods in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> and...</p>
    <div class="s-p" t="1521072536">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFt6FaqqKmwd7d7rXthlIW070" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzobhW2HlSGTcYHHEyIVr2oILh_1iMmTxH7F44pSZRJRlt_xnYiOmYzbu6XpVujPVNehdf0O6NMtcc45IXRODBMNB2wIy3b5emYZ3vvaOWbqNS6wWsytXe4aUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4yGEW4Je6O6aLExtOx3rQQBuXOXJgXFc2jRgWgdfw9Pw/0" data-isV="1" uigs="article_account_0">阿里技术</a><span class="s2"><script>document.write(timeConvert('1521072536'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-bbc034987befa91bd217120928089d6f">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9oVamvGdBr1Gv9LYVCK5u4j2aHkyS6qFwXZm3Gd1gBPwLYp6kyVITd9LD5c2v-FAj02EQTFQ4BE-IDXfz7rhT1cfzGmlhQWBS4i0Yo8lE-D6wbcGZG2RMjke9G1jgC-YPvjBD1XUDEB12GJKoBN0IFA4o1b1EtGvja4v3SBBzSc1e0WC6Sbi7DA..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/OB7ib81EAicrTvQbBXEQpf7HAtuz23yse2FvOXibfctibPD49X8YnNE8fH44Tdl5micXHibL1yM8iawhj3SVXSMqGwnqw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9oVamvGdBr1Gv9LYVCK5u4j2aHkyS6qFwXZm3Gd1gBPwLYp6kyVITd9LD5c2v-FAj02EQTFQ4BE-IDXfz7rhT1cfzGmlhQWBS4i0Yo8lE-D6wbcGZG2RMjke9G1jgC-YPvjBD1XUDEB12GJKoBN0IFA4o1b1EtGvja4v3SBBzSc1e0WC6Sbi7DA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOQbbroo3zOckntgl8PYm*h-giNsEQaQJFxUiBXYHEwfXNeZuHmlu29yZqO9HQxS-bJ3tgqo7g4D6ppVDk91A3T0s8MCvzQ9uFv6n1B-C41qyPa1TEtrJOTryCjJNYPKUHbp8nrGKcLwj4VRfBM-eNHQVImUT0ln6j6aygBwIwPcM=">谷歌18年博士生奖研金出炉,八位入选华人学生均毕业于国内高校</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">(Machine Perception, Speech Technology and Computer Vision)☞ 自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>)☞ 隐私和安全(...</p>
    <div class="s-p" t="1523676561">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt8wGd9ocEDzohwKzeY1ZUTs" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzVliYEK9KlnQhIxQwYnGgT0lcATlVQ5v4BzaI2N6DxPUaQFeJFvtyRo4GRSAFqbe6q0qEHttbkGJ6JBf4wmn7NR1WRpp4-IgRkWlUc5qWIMRM5jMObiCny2RTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM66qG2SiaDEX27eEZBbYcRmUgmFFEia4waM9dRPrPVcfYzw/0" data-isV="1" uigs="article_account_1">募格学术</a><span class="s2"><script>document.write(timeConvert('1523676561'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-1804dfbfe22e3cda9232ff08c3ab99b9">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9EKSbghhsxKfzocBij9sxiMjCJuRKTRrhQw13FI-RQp3d0GlHADigl86ArGdAYkezbAIVOv4X-egl3s3l9j5idanVPKE2p9YbI5saJ_up_OuVq0fSD9GblBUx8W25kpHikNN_ygphnEprGSxSCKRSeO6ncOghFq8qcSHgaE5rt6hCy6umSSPEsg..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/4nqn1KN0cA7eCJAj7W3krl0wmUK4Ps3wOkDo0ic51p5DuzR60Ge7yHt7gM0pPibzFEH0GUz2Zicp62X3lxRNibHn6w/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9EKSbghhsxKfzocBij9sxiMjCJuRKTRrhQw13FI-RQp3d0GlHADigl86ArGdAYkezbAIVOv4X-egl3s3l9j5idanVPKE2p9YbI5saJ_up_OuVq0fSD9GblBUx8W25kpHikNN_ygphnEprGSxSCKRSeO6ncOghFq8qcSHgaE5rt6hCy6umSSPEsg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOBW-VsdjlB4l1g0Xg3A9g8CYAYqjoTvVdC8rXXokt*CW8zaC*onFHWLgicjdrR*iUbG1JCX3R*D8fTVS8*xEDiJ4eIigC8ZbaX5KJqofHy1gvtusJVcj1RE*fz1Y5BgJWRqbMUBzMnyF3qNl3kkp0BsX7U7H307DV-4*lpE337lQ=">NLP详细教程:手把手教你用ELMo模型提取文本特征(附代码&amp;论文)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">//datahack.analyticsvidhya.com/contest/linguipedia-codefest-<em><!--red_beg-->natural<!--red_end--></em>-<em><!--red_beg-->language<!--red_end--></em>-<em><!--red_beg-->processing<!--red_end--></em>-1/#data_dictionary 注:数据集中的多数脏话...</p>
    <div class="s-p" t="1555632334">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFt5IPdHGuUwFu_ClNl_1Yoxg" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzHhNWuE0q0VZtq3foc_NaL8kFpZh7_b4IUtNg1Ol1YT4ZI9Rvbj_DKleq99BXI9GOn90lMMGHUjMTN7myxsQby5vTW9Y_e-uYz82N4enc0cQZb6uBN3mgAW4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM61cnqdIKq6yfwsa2ibd82h7ibDbD66IibwcCjVO8VPry8Lw/0" data-isV="0" uigs="article_account_2">数据分析</a><span class="s2"><script>document.write(timeConvert('1555632334'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-956589731677b981ae7de8a5d5e51481">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9szbivErKQQMJb2ENwiK9A7agyO3JuKMmEo7gE_Gdf6EhwEiluXouwkB4Urek1qmvfB93-X5ufEApPPxcoUj-qH3dvm0wiYozKYDQIedMMp8bsz5gEFBHPcMd3aC1qjuqD7PVQ_a6xWK7bOFj5jwRPnmTwm4IDuTY5aB8OtPe95wCYioxHkzTmA..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/KmXPKA19gWibUDCv3nC2sIyw2IyI9yVuJQ50MY6FYibsx5lH9FkcLgmJaOzYvne5HDtx9VicOJ8BtOzr9IjrNwpPw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9szbivErKQQMJb2ENwiK9A7agyO3JuKMmEo7gE_Gdf6EhwEiluXouwkB4Urek1qmvfB93-X5ufEApPPxcoUj-qH3dvm0wiYozKYDQIedMMp8bsz5gEFBHPcMd3aC1qjuqD7PVQ_a6xWK7bOFj5jwRPnmTwm4IDuTY5aB8OtPe95wCYioxHkzTmA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO12VXWc5T7So3IHmcjQxEYNbVTNhSjYHxwJ8s5ArbxCQaqVWNRVw4vGwkijxxw7DSiBG35DWfNrIXu9WaQ5*a2yOxpXzIIliRYMNRP*k1UYVM-hIwuIYVh2SOERqGoAHXKnA3*ZVCs2zEhn2MjG3S0srD70KFudckhf0srjidTTI=">李彦宏登上时代周刊封面,百度研究院全面升级</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">Center 工作.Church 创立了自然<em><!--red_beg-->语言<!--red_end--></em>处理领域最重要的学术会议之一 EMNLP(Empirical Methods on <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>)...</p>
    <div class="s-p" t="1516330678">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFtyH4wzDYSYFwlcMk8znCtfw" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzRGLZIEUzJX_qOWODnETUR8bTIFw0JvUdInDmj3SPFza0m3lasfxChdRNDh94disQotE5uOuK0PKpJPp9VfuAj6z3iIgUW7UQfiA4iaH8rDrWGWpmld6JGqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM75UiawQgcdqOcmtYS7Jibug9J7dskxkNicGiadtdKl7mLyiaw/0" data-isV="1" uigs="article_account_3">机器之心</a><span class="s2"><script>document.write(timeConvert('1516330678'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-da491ed65884576cdabcbbdbe9bc72ef">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9ENQyVsuq8QLTayMPzSynihffGb7JldyafSW85_RlCctwzI15Ym5Ws5CdBiGqgUSkMlGL-1PHuLoQxuhZBu90jSzKe3tR5rF1r5QYKPfxJX9HOc9V6E5Igs8XEBBfZScqOy61ONeNWcEuH7FPR85W4pp_jCzM3LFo-Kuwe7s6X04tPujwwRB2Pw..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/L4LJPfaSIKeMNDCHTvCqrjn0wgVxaIrsNeBR9ppmiciaa3ByJeeMiafH3iceicP2QOdd3BQl6tIlsqsX8gKfzC3ibXww/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9ENQyVsuq8QLTayMPzSynihffGb7JldyafSW85_RlCctwzI15Ym5Ws5CdBiGqgUSkMlGL-1PHuLoQxuhZBu90jSzKe3tR5rF1r5QYKPfxJX9HOc9V6E5Igs8XEBBfZScqOy61ONeNWcEuH7FPR85W4pp_jCzM3LFo-Kuwe7s6X04tPujwwRB2Pw..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOhiCQwS*jEHGv7IbNkNeamMKY0NVa-DSN*lPwFMIWiSQ3Bc*Na6d7qQmIQMIwAFehq2sW29yoInQHlE09iQkSL65Dtjf476V7pKxMybldPIffYN4UCmzLJln-qLETKF8ssDimXzGKoXRbdyxrEtUWccESj3KDpCEXaG5csBAsVcc=">每日听写|1.21</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">competition, machines that used AI performed better than human beings in a high-level reading test.Two <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em> ...</p>
    <div class="s-p" t="1548021621">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt0c4dtCWXTrCnKUzTiKe82o" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzTKR54KlqJDVMDTbx2dqzWu-zuanLxvuXCmDjK2D7541hDlTc23OhSSkOR-IBIsgmPnIKeG3r918w6Gyetg1Erl4CmkmSYQPkNUoA6ykMHrzTB1LOfbvZO2RTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7sLlI6oicz07ekvVjGuT5fRstic6OcicxYtYY64kcg7KDgg/0" data-isV="0" uigs="article_account_4">TeacherGwen</a><span class="s2"><script>document.write(timeConvert('1548021621'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-c870ddc9b92166d2dc4d3664b097093a">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7pwF2gSEqItV0s-SM7BF2ne_0EWECdSAF5jUfZh6CPt3shJ6pu7jwqxgQwKdfzhDjmVv_364ABbS9Ebe5gu8_rH36j1J-PmOEv6sJoQMwvDoHhcpD4bxN5Xy08OLTBhW0A..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/UicQ7HgWiaUb1b1anvefgWOQHz5lxaSWVQsqt97Qu6PL6TQ8XPFqr1ibSzbTUT6wRH46h3BvoGNUK1Oj1DNLjCGsQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7pwF2gSEqItV0s-SM7BF2ne_0EWECdSAF5jUfZh6CPt3shJ6pu7jwqxgQwKdfzhDjmVv_364ABbS9Ebe5gu8_rH36j1J-PmOEv6sJoQMwvDoHhcpD4bxN5Xy08OLTBhW0A..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOgeItqUApjgMEtbjB4rdbLnpYWY3wCO-KopRoXKOEO9yq0vIwvCFjz8dX4S6xtmiAYeneNN595ubqT27MaJD9lTLBWnScexlJVKs3DUVTctqbaQEuiOaZV4Z2SBgo6I5xf3bxw4xK1X8eJ0fUHjQ*8dz216ojM1ebC60IsMSHvRI=">【干货】适合NLP初学者的8个免费资源分享</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">2 | 自然<em><!--red_beg-->语言<!--red_end--></em>处理&mdash;&mdash;微软 格式:课程地址:https://www.edx.org/course/<em><!--red_beg-->natural<!--red_end--></em>-<em><!--red_beg-->language<!--red_end--></em>-<em><!--red_beg-->processing<!--red_end--></em>-nlp-3 简介:这是一个自学的学习...</p>
    <div class="s-p" t="1561956033">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt_3tpR1cD_MGm5ljX55Ax5c" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzViSEkacHRFSKCx5M6WPU9IiKMn1vwlifhlsQEmUocDHUlvTfZtFTmyhc1lIRO1PSb88B4w5eYxyCY4UtGOwNTTonJ4avsjm6jVxqWvBdRMz4ysFTJOK9RuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5Ge0ZibsJqTzd6HdTSHcydlic4TnsmpJicUrIlicD1L9ficFw/0" data-isV="1" uigs="article_account_5">新智元</a><span class="s2"><script>document.write(timeConvert('1561956033'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-7e246ea8bae38d0960dcf67f75c13127">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7oeWPW_1AG-EXXJCspA6QPmMHUmARsBMzJqEZrnKEsTdQt4-HwOD2VtAA5iTX7nKbIBh2ioAI2fGM3G2ac6Jw2YALJfGhtom6nmeWCLGMCSkOoWGMKggHFH2CsG6-xMgzQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/UicQ7HgWiaUb2LvHIguNHibxiad7QBplSQPKhOelkOKUkU1MQEOnojdWxxld5whWXJhuicnDS1sWqicYlHiaLw3c738yA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7oeWPW_1AG-EXXJCspA6QPmMHUmARsBMzJqEZrnKEsTdQt4-HwOD2VtAA5iTX7nKbIBh2ioAI2fGM3G2ac6Jw2YALJfGhtom6nmeWCLGMCSkOoWGMKggHFH2CsG6-xMgzQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOgeItqUApjgMEtbjB4rdbLsb*iftDmgYAfsNZ*h9FfN-ixKdO-Fj-IA1uiXqSzpPvttzV5C03ovfBS1TABvQbYRMbreSeFQK*s2C3HeMD5Kjc-jmVi6TifszYnGzoZ*y4dZHzHTN-6QX91bHbj4DFkr5Ot768kILWcqFKssIE1QA=">如何快速跟进NLP领域最新技术?(文献阅读清单)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6"><em><!--red_beg-->Processing<!--red_end--></em> (3rd ed. draft)Dan Jurafsky and James H. MartinNeural Network Methods for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> ProcessingYoav Goldberg课...</p>
    <div class="s-p" t="1558671514">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFt_3tpR1cD_MGm5ljX55Ax5c" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzViSEkacHRFSKCx5M6WPU9IiKMn1vwlifhlsQEmUocDHUlvTfZtFTmyhc1lIRO1PSb88B4w5eYxyCY4UtGOwNTTonJ4avsjm6jVxqWvBdRMz4ysFTJOK9RuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5Ge0ZibsJqTzd6HdTSHcydlic4TnsmpJicUrIlicD1L9ficFw/0" data-isV="1" uigs="article_account_6">新智元</a><span class="s2"><script>document.write(timeConvert('1558671514'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-95c9a55e24d352a2d95f825d7aa96c15">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9F_Ym0htqnOTaafu9LZgAi1uUh2PhBWuavS_HRaxOyc3DZpzEH_hzY3F3rh-1ZtAL8fN3xwumH-hhM92MF0Wt5q7S3qlrl3Kll877cq28VVqWyaZ0FpkixHR8VDpABqkE3kEriyRoCKnKHoT3gpWS8Iy_fslLohehTPD_xXMvaWDI3OTRHYU2og..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/3OyBh4rghGCLDOVwRlV4sOXUNlS6P5FPftfwOcicAsWCYdN6UBiboiarftNXsULey15weJ60INjJPVPIvJAS65mjQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9F_Ym0htqnOTaafu9LZgAi1uUh2PhBWuavS_HRaxOyc3DZpzEH_hzY3F3rh-1ZtAL8fN3xwumH-hhM92MF0Wt5q7S3qlrl3Kll877cq28VVqWyaZ0FpkixHR8VDpABqkE3kEriyRoCKnKHoT3gpWS8Iy_fslLohehTPD_xXMvaWDI3OTRHYU2og..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOdee-w8-7*9z*F4H6Jrqrcvifk*Sbf0wfrdUWejH5qmsJTXTxZdwS5M06JoG5-Pyl5XsFs5EU8RJjUrJJvR6fatI6EcfnCfCGa0*fSus2nqs9zseHXA2DyzR1ZHqbVKLsyvulBqWLRfqYz9sGjkUTDVzUEKZLG9fv*jRakdYG-DU=">人工智能系列一:AI发展渐入高潮,未来有望引爆新一轮技术革命</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">&ldquo;听得懂&rdquo;问题,机器翻译、问答系统和文本摘要是其主要应用场景.自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,简称NPL)主要...</p>
    <div class="s-p" t="1540292314">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt7dqTLQMNmSypuwGb5KVPbk" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzrJVYuT77MBkYp3pzSoVhUtyQS0dL2iG-a4b78z0riTPb4CDkGbObcfKGRqY8f1_L_3XunKAF3r7Qby9IxnQPyvpkW_46ZGVU1iCdSixT-Z5F0dv21Bo4SWRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7GbhiaoutXwRfjQsnI5REj3qdjpJoHEIOyia3pCMiba4KXA/0" data-isV="0" uigs="article_account_7">泽平宏观</a><span class="s2"><script>document.write(timeConvert('1540292314'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-b98a085860e671fdc0b2e7db321ba7c1">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YQ_AN1HKO5msowFxqoNFwRH8ktLJk8hWbmVwDp6mq-CDSAezycbti9ouGtwhes_pMpcUhK-fp-SjrlXMCHaiX1AtM13uJgl7ZEtqmJf4KAg2j_K6q6jorwal6ZiPFs7Nq9GUDuWThH0YhRSgh1_O9xs5N7rQOTOZgj6dslz5RibzAjcIGepUqA..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/BnSNEaficFAbIIBWLwqqWNB6sdqHdTUYJQ7S2icBhfftbLjs45icF5hEgJLIMlcvQaf3hxTG4vFu1KAI4fDcGibibNg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YQ_AN1HKO5msowFxqoNFwRH8ktLJk8hWbmVwDp6mq-CDSAezycbti9ouGtwhes_pMpcUhK-fp-SjrlXMCHaiX1AtM13uJgl7ZEtqmJf4KAg2j_K6q6jorwal6ZiPFs7Nq9GUDuWThH0YhRSgh1_O9xs5N7rQOTOZgj6dslz5RibzAjcIGepUqA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOS7Q2Y533D-uSOhTNDKqFZ5NGvNlPItgHIiEpUW278MJAO2GUH-DVe45mRAYLUmCeKmZt*qKuwtgmH3VtKEOvBL8cBvRYv3pHuHN2ETg*SckMune9XYzfRhWxZBMZeE4Yxu3f1AVbuNKbjmi8*MhhqRwTlim0RBufQCZWCSwQslw=">上不了北大&ldquo;图灵&rdquo;、清华&ldquo;姚班&rdquo;,AI专业还能去哪上?</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">Machine Learning &amp; Data Mining(机器学习与数据挖掘)、<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>(自然<em><!--red_beg-->语言<!--red_end--></em>处理)、The Web &amp; Information ...</p>
    <div class="s-p" t="1561608156">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFt0s0lb4YYVldJ17r7KZLOKI" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz0Z4DBn4Zh0dhZ1RLwSLiLgu4t3bHnxkfGKRCJqwJ0Wxf-EelY8fdwWTnmB7Qll5B78Y3VXiaQuJ9tum8PhUhlIRGiDlm9tkBlgIE2BnNhByCCgfMeVNP-GRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7Zq0tOhrfGW6nuvYPTqOhUZxHKmopuzUG20yvzWRriaMg/0" data-isV="1" uigs="article_account_8">AI科技大本营</a><span class="s2"><script>document.write(timeConvert('1561608156'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-18dea2b951b0dc18a859413086a4fd39">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9KxkLcoo1mNffJKVtP-J2bHmvodHGeurR86Mb5jjWh2czqeEWLS77Qe_40y4s-b5GtxnQ_XFnhWNM1NEf0iWr-SrhBs1FXS6eJam7jpqhSLWy4Vm7bGvqRxwC0JfAAELQ5BOnUp98iT-hqvPIMjMH1D0ep7q4XqqBBULJuwv1ikNr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/Z6bicxIx5naJslEubr7iaL7ZsoRQpYj6YPEsVlAUlB2WypVgZOdZQAnTvbBLoIKA6vKLiaZ4nZpvwjr0UL0NQvd1Q/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9KxkLcoo1mNffJKVtP-J2bHmvodHGeurR86Mb5jjWh2czqeEWLS77Qe_40y4s-b5GtxnQ_XFnhWNM1NEf0iWr-SrhBs1FXS6eJam7jpqhSLWy4Vm7bGvqRxwC0JfAAELQ5BOnUp98iT-hqvPIMjMH1D0ep7q4XqqBBULJuwv1ikNr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOuh6DOda6rDnGk36sGhtiXDh2Ufa90ZEbIuSCfFIAflU-g-YZAKZ1bfNGNZGsFrtx8ebVzOllDJexg70ZcQ0h6MjbeWEG5YLV7i1cZhw2V7jjdV8vJlCOAIs7L4fQmbXp6QyhguSxo36ZTjhlxlHD0T7Nm8hJOWyn7Dra3*Ss09g=">知识图谱数据构建的&ldquo;硬骨头&rdquo;,阿里工程师如何拿下?</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">learning for relation extraction. In Proceedings of the 2012 Joint Conference on Empirical Methods in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> and...</p>
    <div class="s-p" t="1520986089">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt6FaqqKmwd7d7rXthlIW070" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzobhW2HlSGTcYHHEyIVr2oILh_1iMmTxH7F44pSZRJRlt_xnYiOmYzbu6XpVujPVNehdf0O6NMtcc45IXRODBMNB2wIy3b5emYZ3vvaOWbqNS6wWsytXe4aUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4yGEW4Je6O6aLExtOx3rQQBuXOXJgXFc2jRgWgdfw9Pw/0" data-isV="1" uigs="article_account_9">阿里技术</a><span class="s2"><script>document.write(timeConvert('1520986089'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=5&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			
    				<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a>
    				<a id="sogou_page_2" href="?query=natural+language+processing&type=2&page=2&ie=utf8" uigs="page_2">2</a><a id="sogou_page_3" href="?query=natural+language+processing&type=2&page=3&ie=utf8" uigs="page_3">3</a><a id="sogou_page_4" href="?query=natural+language+processing&type=2&page=4&ie=utf8" uigs="page_4">4</a><a id="sogou_page_5" href="?query=natural+language+processing&type=2&page=5&ie=utf8" uigs="page_5">5</a><span>6</span><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=7&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约100条结果<!--resultbarnum:100--></div>
    </div>
        
    </div>
    
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "null_50-null_51-null_52-null_53-null_54-null_55-null_56-null_57-null_58-null_59-";
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
    <!--1562763693350-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "923d4c5e-2826-40da-b6c5-4ecdb92fd751";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693485;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693485",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "923d4c5e-2826-40da-b6c5-4ecdb92fd751",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A5334BAEE42F2E10",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "7"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-95c9a55e24d352a2d95f825d7aa96c15">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9F_Ym0htqnOTaafu9LZgAi1uUh2PhBWuavS_HRaxOyc3DZpzEH_hzY3F3rh-1ZtAL8fN3xwumH-hhM92MF0Wt5q7S3qlrl3Kll877cq28VVqWyaZ0FpkixHR8VDpABqkE3kEriyRoCKnKHoT3gpWS8Iy_fslLohehTPD_xXMvaWDI3OTRHYU2og..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/3OyBh4rghGCLDOVwRlV4sOXUNlS6P5FPftfwOcicAsWCYdN6UBiboiarftNXsULey15weJ60INjJPVPIvJAS65mjQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9F_Ym0htqnOTaafu9LZgAi1uUh2PhBWuavS_HRaxOyc3DZpzEH_hzY3F3rh-1ZtAL8fN3xwumH-hhM92MF0Wt5q7S3qlrl3Kll877cq28VVqWyaZ0FpkixHR8VDpABqkE3kEriyRoCKnKHoT3gpWS8Iy_fslLohehTPD_xXMvaWDI3OTRHYU2og..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOdee-w8-7*9z*F4H6Jrqrcvifk*Sbf0wfrdUWejH5qmsJTXTxZdwS5M06JoG5-Pyl5XsFs5EU8RJjUrJJvR6fatI6EcfnCfCGa0*fSus2nqs9zseHXA2DyzR1ZHqbVKLsyvulBqWLRfqYz9sGjkUTDVzUEKZLG9fv*jRakdYG-DU=">人工智能系列一:AI发展渐入高潮,未来有望引爆新一轮技术革命</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">&ldquo;听得懂&rdquo;问题,机器翻译、问答系统和文本摘要是其主要应用场景.自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,简称NPL)主要...</p>
    <div class="s-p" t="1540292314">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFt7dqTLQMNmSypuwGb5KVPbk" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzrJVYuT77MBkYp3pzSoVhUtyQS0dL2iG-a4b78z0riTPb4CDkGbObcfKGRqY8f1_L_3XunKAF3r7Qby9IxnQPyvpkW_46ZGVU1iCdSixT-Z5F0dv21Bo4SWRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7GbhiaoutXwRfjQsnI5REj3qdjpJoHEIOyia3pCMiba4KXA/0" data-isV="0" uigs="article_account_0">泽平宏观</a><span class="s2"><script>document.write(timeConvert('1540292314'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-b98a085860e671fdc0b2e7db321ba7c1">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YQ_AN1HKO5msowFxqoNFwRH8ktLJk8hWbmVwDp6mq-CDSAezycbti9ouGtwhes_pMpcUhK-fp-SjrlXMCHaiX1AtM13uJgl7ZEtqmJf4KAg2j_K6q6jorwal6ZiPFs7Nq9GUDuWThH0YhRSgh1_O9xs5N7rQOTOZgj6dslz5RibzAjcIGepUqA..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/BnSNEaficFAbIIBWLwqqWNB6sdqHdTUYJQ7S2icBhfftbLjs45icF5hEgJLIMlcvQaf3hxTG4vFu1KAI4fDcGibibNg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YQ_AN1HKO5msowFxqoNFwRH8ktLJk8hWbmVwDp6mq-CDSAezycbti9ouGtwhes_pMpcUhK-fp-SjrlXMCHaiX1AtM13uJgl7ZEtqmJf4KAg2j_K6q6jorwal6ZiPFs7Nq9GUDuWThH0YhRSgh1_O9xs5N7rQOTOZgj6dslz5RibzAjcIGepUqA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOS7Q2Y533D-uSOhTNDKqFZ5NGvNlPItgHIiEpUW278MJAO2GUH-DVe45mRAYLUmCeKmZt*qKuwtgmH3VtKEOvBL8cBvRYv3pHuHN2ETg*SckMune9XYzfRhWxZBMZeE4Yxu3f1AVbuNKbjmi8*MhhqRwTlim0RBufQCZWCSwQslw=">上不了北大&ldquo;图灵&rdquo;、清华&ldquo;姚班&rdquo;,AI专业还能去哪上?</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">Machine Learning &amp; Data Mining(机器学习与数据挖掘)、<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>(自然<em><!--red_beg-->语言<!--red_end--></em>处理)、The Web &amp; Information ...</p>
    <div class="s-p" t="1561608156">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt0s0lb4YYVldJ17r7KZLOKI" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz0Z4DBn4Zh0dhZ1RLwSLiLgu4t3bHnxkfGKRCJqwJ0Wxf-EelY8fdwWTnmB7Qll5B78Y3VXiaQuJ9tum8PhUhlIRGiDlm9tkBlgIE2BnNhByCCgfMeVNP-GRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7Zq0tOhrfGW6nuvYPTqOhUZxHKmopuzUG20yvzWRriaMg/0" data-isV="1" uigs="article_account_1">AI科技大本营</a><span class="s2"><script>document.write(timeConvert('1561608156'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-9e6d1dc123a5bdf6d934569481621132">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7rjFR9R0KWkkXGuj-tgRzS7sEVdOD9hNywQjYfIOVC0tJowyR_aOMOIQYLigOUWGynXt_lEyfsFm0kaoiTnFC1GDFr_qpCiCSpp_yweY2ZFxH4IxbhoHNqd6VKrzu_4XKA..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/UicQ7HgWiaUb2ibUKFq98Wib7C0TQxibyE3EVWbibEzqkiaB8arZIFM9z0pVCpvq6tSibONVG8G4ckOTu8lddQtZicpIFPQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7rjFR9R0KWkkXGuj-tgRzS7sEVdOD9hNywQjYfIOVC0tJowyR_aOMOIQYLigOUWGynXt_lEyfsFm0kaoiTnFC1GDFr_qpCiCSpp_yweY2ZFxH4IxbhoHNqd6VKrzu_4XKA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOgeItqUApjgMEtbjB4rdbLmLbBKLAkvD9NHmvWFcZ8qJMbWkHy7M1CGeJUMdLR8b6iINqihCEtLxrJ08iKjSy5xdD4vqqhl0cfaUF37TWkZOj3t7gx-VpOmZVnoxzDjLhGslEKuOcyqtsv8JRbHN2Rpcj-DMXY5Sc36LXFN8b0yY=">【AI志愿超强攻略】中国高校人工智能专业最全院校排名&amp;课程对比</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">Machine Learning &amp; Data Mining(机器学习与数据挖掘)、<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>(自然<em><!--red_beg-->语言<!--red_end--></em>处理)、The Web &amp; Information ...</p>
    <div class="s-p" t="1561525378">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFt_3tpR1cD_MGm5ljX55Ax5c" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzViSEkacHRFSKCx5M6WPU9IiKMn1vwlifhlsQEmUocDHUlvTfZtFTmyhc1lIRO1PSb88B4w5eYxyCY4UtGOwNTTonJ4avsjm6jVxqWvBdRMz4ysFTJOK9RuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5Ge0ZibsJqTzd6HdTSHcydlic4TnsmpJicUrIlicD1L9ficFw/0" data-isV="1" uigs="article_account_2">新智元</a><span class="s2"><script>document.write(timeConvert('1561525378'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-18dea2b951b0dc18a859413086a4fd39">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9KxkLcoo1mNffJKVtP-J2bHmvodHGeurR86Mb5jjWh2czqeEWLS77Qe_40y4s-b5GtxnQ_XFnhWNM1NEf0iWr-SrhBs1FXS6eJam7jpqhSLWy4Vm7bGvqRxwC0JfAAELQ5BOnUp98iT-hqvPIMjMH1D0ep7q4XqqBBULJuwv1ikNr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/Z6bicxIx5naJslEubr7iaL7ZsoRQpYj6YPEsVlAUlB2WypVgZOdZQAnTvbBLoIKA6vKLiaZ4nZpvwjr0UL0NQvd1Q/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9KxkLcoo1mNffJKVtP-J2bHmvodHGeurR86Mb5jjWh2czqeEWLS77Qe_40y4s-b5GtxnQ_XFnhWNM1NEf0iWr-SrhBs1FXS6eJam7jpqhSLWy4Vm7bGvqRxwC0JfAAELQ5BOnUp98iT-hqvPIMjMH1D0ep7q4XqqBBULJuwv1ikNr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOuh6DOda6rDnGk36sGhtiXDh2Ufa90ZEbIuSCfFIAflU-g-YZAKZ1bfNGNZGsFrtx8ebVzOllDJexg70ZcQ0h6MjbeWEG5YLV7i1cZhw2V7jjdV8vJlCOAIs7L4fQmbXp6QyhguSxo36ZTjhlxlHD0T7Nm8hJOWyn7Dra3*Ss09g=">知识图谱数据构建的&ldquo;硬骨头&rdquo;,阿里工程师如何拿下?</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">learning for relation extraction. In Proceedings of the 2012 Joint Conference on Empirical Methods in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> and...</p>
    <div class="s-p" t="1520986089">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFt6FaqqKmwd7d7rXthlIW070" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzobhW2HlSGTcYHHEyIVr2oILh_1iMmTxH7F44pSZRJRlt_xnYiOmYzbu6XpVujPVNehdf0O6NMtcc45IXRODBMNB2wIy3b5emYZ3vvaOWbqNS6wWsytXe4aUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4yGEW4Je6O6aLExtOx3rQQBuXOXJgXFc2jRgWgdfw9Pw/0" data-isV="1" uigs="article_account_3">阿里技术</a><span class="s2"><script>document.write(timeConvert('1520986089'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-af1344c1841ba7da38a995a2d790365b">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9FdI64as_iHBs9O9Cgf_vmPVsYR0JylZQDt-_x7oytQ03Hr5AdhGoJa6RpuycsyhOi5rRTXx5OMu4SfdePQazKrMIQP0LiUr_tURdJCY1T0QqOLdQd2k9_dFLuzcnHfuhzcO7A-k0_rtIXhK1fgS4L-NSnIX48UWzp5yVVy6AH5nP28temKTOwg..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/OL321y9K1n9BSSd2QibicnrUTFAIMiczufcc0xsRZwglsgQjxxDyUIn3EL6u6zzh3KiaaBHEGlc17picfx24a6ZrUvA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9FdI64as_iHBs9O9Cgf_vmPVsYR0JylZQDt-_x7oytQ03Hr5AdhGoJa6RpuycsyhOi5rRTXx5OMu4SfdePQazKrMIQP0LiUr_tURdJCY1T0QqOLdQd2k9_dFLuzcnHfuhzcO7A-k0_rtIXhK1fgS4L-NSnIX48UWzp5yVVy6AH5nP28temKTOwg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOBld9c7fPK*ailRIhYt4wYQ8lic6AhwEfm8d86HbDhF3R22Db7zl-ARQpL*rthZgpwA2o9O1y0qPpnbo6K5JZWRjK4ct1*F3p2DpqRN4CZhiX-mh6yQmQrMvsTJG6SjLWpgmf6EXtTJtRb12J*i1oe48YOR1ZzsGL2uXjUHrX8VI=">致正在填报高考志愿且对人工智能感兴趣的你</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">Machine Learning &amp; Data Mining(机器学习与数据挖掘)、<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>(自然<em><!--red_beg-->语言<!--red_end--></em>处理)、The Web &amp; Information ...</p>
    <div class="s-p" t="1561294561">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt23o55LUwt-lZ3ZGs7kFH5E" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzGpM2b8W9CTJcMOI-n0PhjWtZ_ss2IdqfSJnUagvNcb56aUcemdBIcC-dE9gjmLw22D__GSnmJfUkF7noLtz9d8p_BafdLqKYGDlys8JIktSK9cXsIV43nOO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4NeH55HHjdGAeg5ic1wEJjicAajhic3OWGJd88sp1crsicog/0" data-isV="1" uigs="article_account_4">清华招生</a><span class="s2"><script>document.write(timeConvert('1561294561'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-a99c25c507c28f6c9895794124797236">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9HoXjV883cCmbh61bsMeX7-Kfr4TSpzEWQx9im6PDcoX7a7DbLJmKH0PN3B92l4ifmPmQTBCLaRsdyhi5Z4omaMVD9RKtbgwuA6Qcjyvujxol-oXwwfwEFWoN-SVK930MUXvdBiDOX64UYDKGTFiiVgSwBo9kPEIOsrEvl4iDrdvI3OTRHYU2og..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/9CJSDicUiaYtJGZSdSia9pyIyNO34TX9EZsJjOb3AmpiaKj49zbgMm2quRQ1Wy2RSkz07rypC10HhmVblQ85k3nmUg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9HoXjV883cCmbh61bsMeX7-Kfr4TSpzEWQx9im6PDcoX7a7DbLJmKH0PN3B92l4ifmPmQTBCLaRsdyhi5Z4omaMVD9RKtbgwuA6Qcjyvujxol-oXwwfwEFWoN-SVK930MUXvdBiDOX64UYDKGTFiiVgSwBo9kPEIOsrEvl4iDrdvI3OTRHYU2og..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOLmZxOdqI5CVMu28FCjQtJbPp5-nSTiDRZhjtFzQAREX9quVnK*SeRMdCL*oN*xs3iftXbym4clM*NQQWn1PkIBYvoyWVdFm7EDX*WNXePlHYlwFuPzUodHe6i0nDwLKTYmR3FF5Gf*t1rqZ*X0eWeXlZcG958oyHD41UrCtA7zY=">剑桥小哥哥李泽辉:让Siri、小爱同学、小冰们更懂你, 人工智能少不了这项技术</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5"><em><!--red_beg-->language<!--red_end--></em>,＂ says Zehui Li, a Year-4 student of Computer Science with AI. He will study <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> (NLP) - a branch of...</p>
    <div class="s-p" t="1561606244">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt4V4S_YOgYWe5DQhbpMmjmw" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzEy66vgytzm9GiPOQHTx37z4Rm7bpboA1ZDJzVUL6MkqHHFacWBThNUHNi3nkhNxuG8SR6E3-CU0Oj6dZvNf7h9GFjMGaofkKo_SAp6yo2VcB_rxAhJCUmeO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7kmEILCtzXZwSx2EMcnSM2ciaQmf9qkZ8WoTNUzHTTHpA/0" data-isV="1" uigs="article_account_5">宁波诺丁汉大学</a><span class="s2"><script>document.write(timeConvert('1561606244'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-0f0f122ee22c193110d119387b1a43df">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9PaBqmwPGR9en_-6HIxq90yRu1S0Y1u0z4AtdVWqoWf77VwrxUADYXRR9QrWzS_TdDaoZv7aPAySwGJJ_0E7QhcjZoMTXqTRCHdreK5JShAh-Zam4kg5ilo9riQhZuF1MwCldBztcPRg-CmEvZ1bMf4Qi_JorVdIMQZVwW2gG_LaTJmCU1UgHwQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtALr05ejXyKCRsaCAlU2wF5ASdAmzeibVjE8LaT4T9gXhNibY0MXuF7dUg8SIg7pVNxyk2HVkg6ReLw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9PaBqmwPGR9en_-6HIxq90yRu1S0Y1u0z4AtdVWqoWf77VwrxUADYXRR9QrWzS_TdDaoZv7aPAySwGJJ_0E7QhcjZoMTXqTRCHdreK5JShAh-Zam4kg5ilo9riQhZuF1MwCldBztcPRg-CmEvZ1bMf4Qi_JorVdIMQZVwW2gG_LaTJmCU1UgHwQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOnkoXf78xa8g15u2vWFH4J1r2ci4SdTe9gFc8U3R8YlLLdb56ZLOHVkwbZ90iE-BvPglVNwFx92fI1I4SMmBe-AEBka2yZSE-6usdfdQOeLjQM-GX23BAjGOPcDOajoLakuTkUII2z9f7zvy6Ef1fEP-Qr8q-o5azYQ1hYqtvsSc=">这套1600赞的NLP课程已开放,面向实战,视频代码都有丨资源</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">一套面向实战、号称&ldquo;代码优先&rdquo;的NLP课程来了,名字为A Code-First Introduction to <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,fast.ai出品,全程...</p>
    <div class="s-p" t="1562653598">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFt5XbBRNu0lfpuqkODS4ZSL8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdze01PiBNnJ4wnw9RX0O5z4LGJhI_0xaBwwjbzUwZGQaBds3McnebLy26-jJC2mTVOdno7LD0qU3tlRUV5ogrkLwCzEbTlOTidHgENlkXkLa3UqYK5Z9J9DqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6PqxX9Yx8MibJ3nial8ialvVrRs3PxhCJm7eWgR7vFrowLA/0" data-isV="1" uigs="article_account_6">量子位</a><span class="s2"><script>document.write(timeConvert('1562653598'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-fc48f68373e0b433e440bf14f3532a2e">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9AewsnkBWcLOrufx2K3Ui8-R9UVwSQOANYxH6pqYlAU1vAecczbwcdt6PCO2-O-ZFS47BEiTofMwsK7vxfx-z7l4E3XMJ-REWEmzNjyQBT79UNeMpWnTfav_FqwEnO9dGVVYmMmYoQ45Z0Q7T-fHDOW4GO7TDq5-jYa_VDtryDv7s46dn8Efgxg..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/3QdXlNYeWk0QYK71Ij90CyANxcqGnyvVGCnHYokKiceT8ibhbVOxcooNJibS3lwcMf6AJjpFC9PG0Et2GnYcib4K2Q/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9AewsnkBWcLOrufx2K3Ui8-R9UVwSQOANYxH6pqYlAU1vAecczbwcdt6PCO2-O-ZFS47BEiTofMwsK7vxfx-z7l4E3XMJ-REWEmzNjyQBT79UNeMpWnTfav_FqwEnO9dGVVYmMmYoQ45Z0Q7T-fHDOW4GO7TDq5-jYa_VDtryDv7s46dn8Efgxg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO8nKwtw*U9TmWD20Hp*u5XIvZ12sotNAmxwKMLCUeYcfMHtE5FWOjRjXuBr9Sw41mxqVjTIdMlEpd9l7EdPTxCZ5n7EACzcrQPW7Sf8QanHqb65IITaSBn6vjTmmExbK-20OWlimGgzBmmILrYtF6sXYDDOoy2bo8F1HwwqrQLus=">外企头条丨旅行社是激发灵感的旅游体验设计师丨Bilingual</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">In some cases, machine learning could be aided with voice and <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>.旅行者希望其应用程序或电脑能够根据他...</p>
    <div class="s-p" t="1553320593">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt-SP6ywo5SgukCZRKKSevUE" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzOhjTWxLiJ9yebUtSVyAs2yHtjPSbFhvg3pwZeX8zcbb3bmn-OBPFdPdY6ODXpfW6xBN4WbHK6Kxylwl04UYp9tM5fkyxmLKRZH_BpLDHrsIsh0hmZReiaGRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4lQpicLicOQTU83Kq8iaXuiagcPj6MtST8jatmA8XESwfMGQ/0" data-isV="1" uigs="article_account_7">经济日报</a><span class="s2"><script>document.write(timeConvert('1553320593'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-728ef9b8c5a9a9fd61b16a80cf303248">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9pyexkTqNU7VU7TGLFia_RBusd1rhOG61UWlLcXLv7jqCzKgxr8pnz45bTyYHOEjtET87ap8CJmS5fiZd-Ve06mRepN1iPhqYjwdKFASeJaz1j7ScH4N5PygYESQB8bRoEO9dFgoulzp0Bjv-ZJB5yZwZkzsHGaiXVEpNVfRoyHNr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/pojyAtdhQhMU8ic8zvYTlbnKiaxOKJn7ibTw4Q0yoDFZW7icicp9cv2otpsQMNhfVtXTafZqiblKWytREEmE7ibMZ4sibw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9pyexkTqNU7VU7TGLFia_RBusd1rhOG61UWlLcXLv7jqCzKgxr8pnz45bTyYHOEjtET87ap8CJmS5fiZd-Ve06mRepN1iPhqYjwdKFASeJaz1j7ScH4N5PygYESQB8bRoEO9dFgoulzp0Bjv-ZJB5yZwZkzsHGaiXVEpNVfRoyHNr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOYhwwfh54WODTvWgB-O7vh*ZpjdMjXQnDBLMNfk7nJkLqGFm7MYttk0GfOI*OlmbhubZOb7J2KRmrD14aaALkooDplVgfLwCDQin7F5i6Bc3yZ3wITJPE2XIrb0y8BYdflXKRUS327q5aZ4DSwmDgNfh5hsansMeQAItzj6mRY9M=">平凡而又神奇的贝叶斯方法</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">这里需要用到一个分词对齐的平行语料库,有兴趣的可以参考 《Foundations of Statistical <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>》第13 章,这...</p>
    <div class="s-p" t="1542205636">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFt1kz2UP2SYslaQocYLmPfPo" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzO83OgHBo6AQbxPIWco6SPFNh2LnlbLn4ipiaNDz13Ucp1qCLFEfEfaC-COKO0aTNeHnROHnRKACQS0mEAvi3M-5SNi6zp987XRDIzYYZHGO1bvDZz1lSQuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6k9dGbXhJyL3t8R4RgWn1y8MiaMHuYkm6adHBEB1etdSw/0" data-isV="1" uigs="article_account_8">超级数学建模</a><span class="s2"><script>document.write(timeConvert('1542205636'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-67f888f43865730dc466eaebb2cf510e">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9JZyCptY1CK5sdedJNI_uqwcpF_OztJo9-ABlz2KZQJmX53dzshJCiNFrMqAh-Z9geIVWvwT-XTJySs2e7X3SDBE34uQB_czuClVeIVKQndj0-F0xAep4VWblUAakR_0i1XBbYn4fS6vcgjthHgcfdj_7tQiMoDhJZ43S-vllW9g89kyxDwoXvg..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/MQujiaQBiaUl0pEaJ2e8OK4pKE3Sia8ZicrU1GEicVj1mOwurW9eiagVdib0j1brNhJLdFJ4L5S68WyuibloovXnga6eyg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9JZyCptY1CK5sdedJNI_uqwcpF_OztJo9-ABlz2KZQJmX53dzshJCiNFrMqAh-Z9geIVWvwT-XTJySs2e7X3SDBE34uQB_czuClVeIVKQndj0-F0xAep4VWblUAakR_0i1XBbYn4fS6vcgjthHgcfdj_7tQiMoDhJZ43S-vllW9g89kyxDwoXvg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOXm84Sihr0y1zTE8qfQMnOUoKq6LxN2LTHR9a6uWYlZrYFQ3YDuDpgZ0z0R4VLRVIGxK8jRvJMBP7aMmYEcZmBDNp1x2WUX7SI3EVMN3LKr-BATEZqoO1SiBDOyqsReUHZ0PWBTZNCfgunLrrsh2EryZtjO6dxkHK4ZcIveq8i-A=">吐血整理:出国留学不知道选啥专业,教育部给你划重点!</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9"><em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>; Robotics; Graphics &amp; Imaging Laboratory. 自动化规划与控制;脑机接口与计算神经科学;计算生物学;...</p>
    <div class="s-p" t="1551441675">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt8DLzRUtt_ThHPBo6yaBXgA" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzxT5L5dcqqE4IMEyjxABjGpBFvh6ZU0M8I-B9GvfSd8M8npgm-TuLKjGhdD3uJ8F0o05KwgEC8-NoFunjNYI2nlB8wUrk_FJ_8Qz1a6_ZNFP1GZqFw-wgnWRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4xTtfGpDOQ1Ud9WaRLDnoziaNjoRY2xJ19RIiareibZI1Bw/0" data-isV="0" uigs="article_account_9">美国留学快报</a><span class="s2"><script>document.write(timeConvert('1551441675'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=6&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			
    				<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a>
    				
    					<b style="float:left;font-weight:normal;margin-right:10px">...</b>
    				<a id="sogou_page_3" href="?query=natural+language+processing&type=2&page=3&ie=utf8" uigs="page_3">3</a><a id="sogou_page_4" href="?query=natural+language+processing&type=2&page=4&ie=utf8" uigs="page_4">4</a><a id="sogou_page_5" href="?query=natural+language+processing&type=2&page=5&ie=utf8" uigs="page_5">5</a><a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><span>7</span><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=8&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约450条结果<!--resultbarnum:450--></div>
    </div>
        
    </div>
    
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "null_60-null_61-null_62-null_63-null_64-null_65-null_66-null_67-null_68-null_69-";
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
    <!--1562763693484-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "2a06849e-2532-4729-abb6-68e9cded2b02";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693560;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693560",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "2a06849e-2532-4729-abb6-68e9cded2b02",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A5319C16E42F2EA3",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "8"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-e4f1ef2da349f5a56c0228c80564cb09">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9JjsNYQAqMz-q82an7_NA4uXxldys1mWNVlDIqUWiz4LeKCKE7mA-7QFJSIz6MrNxskuJaakVUFEsqJlpyhhNJ8V9gVHM1l5fmh5c91KpTfvvMX-Ckc53O0u_p2xxwFOUD9Z61yudRYcBw4-yoXX6zZFDdJaVbIzyB5Gsnvfiejk89kyxDwoXvg..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_png/fhujzoQe7Tqk3cpicUVyvEOoCFl8GpoMzNCrvnGkYmvwIbD3UVYXpoREN5VF0TIz7MHaDYI0JYxN74vxS7CicKTA/0?wx_fmt=png" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9JjsNYQAqMz-q82an7_NA4uXxldys1mWNVlDIqUWiz4LeKCKE7mA-7QFJSIz6MrNxskuJaakVUFEsqJlpyhhNJ8V9gVHM1l5fmh5c91KpTfvvMX-Ckc53O0u_p2xxwFOUD9Z61yudRYcBw4-yoXX6zZFDdJaVbIzyB5Gsnvfiejk89kyxDwoXvg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOA6CbmZ3FIAePVWzEn7RT5a85MMX5fj51UigapoW3whjDnTjXYdUrsb8mWfd-3MVPZfMCsBtuz9XvDAw8eE3ik6qLFmkX4OAzZDJl6aJlpHivhUjivAGVRGs0GS1oM57LHHCsKd3lV2T3wglrUkZdVs11gKAWhauZ3YHEU0D3Llg=">150 多个 ML、NLP 和Python 相关的教程</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">(sebastianruder.com)自然<em><!--red_beg-->语言<!--red_end--></em>处理(NLP)A Primer on Neural Network Models for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> (Yoav Goldberg)The ...</p>
    <div class="s-p" t="1502799265">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFt5QBSP8mn4Jx2WSGw_rCNzQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzIo9Az8SqXK3_A_CK13Kujd32TV12-JywQ_RE-jaGdd4j0_G0k9prrqkxxH3XVVo7b3qaLBgVyc2FbFVohY2O5b5PJ9R8mHz_Dahaweb_wtfl2UWz8HmS3eO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6hTCD50H6PaCspsyUarU0oT7bE3evufzsuDKPZxhYFMQ/0" data-isV="0" uigs="article_account_0">Python开发者</a><span class="s2"><script>document.write(timeConvert('1502799265'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-267d0634323311e9f095b29f4b86508f">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nQloB-J4vlHlsnDFmlSAZ9IiPBIa07Vi8QltY1tXuHkiDulX4cfmLZEGTHIkZ5SNv3UldLcfJwXcY1bHJxsu9OZknIAv19OGYE_lKJjDJvyK8CS8JeY3Z06jotuuiAmOIg..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSLrPm5CSlcZia5tvMicicJ97hNGGVIZ1AOhsaZJpdmYlic6dF3ibw3sZRuSHVqWicariasfhQpPD7OohZfFg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nQloB-J4vlHlsnDFmlSAZ9IiPBIa07Vi8QltY1tXuHkiDulX4cfmLZEGTHIkZ5SNv3UldLcfJwXcY1bHJxsu9OZknIAv19OGYE_lKJjDJvyK8CS8JeY3Z06jotuuiAmOIg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaeOM1aO3ceYknqSWbu1*1oZ5dao8rlhiBFFTNM5Vd*Xjxc3SaEaAr5diZ6yaE0rhpu*Xss6Fugbg-pdE7RleGA-gVietmUscELmXHjeFl*2PCK8Kf2dxBr0Inuc-A2kXJqriDnLr*Bx3U43VkkeB4Ho=">【Github】nlp-journey: NLP相关代码、书目、论文、博文、算法、项目资源链接</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">入门必读. 原书地址复旦大学《神经网络与深度学习》邱锡鹏教授. 原书地址CS224d: Deep Learning for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>. ...</p>
    <div class="s-p" t="1562736627">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_1">AINLP</a><span class="s2"><script>document.write(timeConvert('1562736627'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-2893217c49050e4ed5f54d0cd52ffbbe">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9ogEouDJYk3S_Z0v_pCyYGicrwmMI8gzNrDQoiqc-d91XRwbeiCKWGXrfRAy4Ooz4e3I--xSWR61liJLbycyJYBlT5ibSTCYb0o0qDDM20ENzYDDLIOBd2oLr8fkVoNMtOpVMsk4eV1Tazeda9_ZSdKNr_mwS7w-gyfB1BZk6iuGfxjh3za6jWA..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/PLSAhuElFxnbpgGsJyG2Jwez9cBYxf4LPKtouBE1fPKsKApJNoyhb1IYqQnqao73gmlKj56sJEB9qttkic0LAzw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9ogEouDJYk3S_Z0v_pCyYGicrwmMI8gzNrDQoiqc-d91XRwbeiCKWGXrfRAy4Ooz4e3I--xSWR61liJLbycyJYBlT5ibSTCYb0o0qDDM20ENzYDDLIOBd2oLr8fkVoNMtOpVMsk4eV1Tazeda9_ZSdKNr_mwS7w-gyfB1BZk6iuGfxjh3za6jWA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOCKpFefVIJdH6D7HuPyme7a7vdcQFXz-ejxOfIjBIQ6oFocaIy3uoAFkxv1*rKhhYh9oWwiBr3C7OIzCM9-h*i4itlGxRKD5ZNhOkYcFKNSjmhxZY*CBHCW03DaXzM7cQO-vtMu0RqviN9LLVevbvGBkXWwyB83syxHBxl*hJ6v0=">春节送书 | 从入门到精通数据科学,你需要这27本书</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">自然<em><!--red_beg-->语言<!--red_end--></em>处理类书籍1. <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> with Python作者:Steven Bird, Ewan Klein和Edward Loper你将获得原本不具备的...</p>
    <div class="s-p" t="1549252889">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFt98MxFEplSseNeqq-C3iyik" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzrRVFbjfhspK_sfk1hJBAr917QvyvssZzpIBGSs93JwrVMFwN7u6dvay12njYY1Czf4QZFtYjbzTlj04OVVFoO7YIIc4POtgOACVBZiF9q30Vx3hX9S8Q9-O00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6S4LgR8tZVEJcgLu6S1jmmicDwgrpEPa4iaQBJGY8sKyxQ/0" data-isV="1" uigs="article_account_2">读芯术</a><span class="s2"><script>document.write(timeConvert('1549252889'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-286abd62babb88687f4b4ea71f5541fd">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7nHlSOmUhc-a7MSUMe5EGSGEvnUfVVkuXztx3XIOwMJTYVGuO3fqvcVaAhRNtLkxDqcjnw6oIzRxAPRUFRwleC4L4h75mh3sDyq5nhs3_ZO9X0ZxPLdUwFhr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/UicQ7HgWiaUb2mJbIPcMgmP20p0PrPDS4NutHcVqC1jWl2kKwXPs22go6xI2IyLD5BURfIHCDy4BXjlsKeiaAOibibA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd95S4M3TQxOnQMMLXmZn36WeCDyJB1VtSJyGAu9UYrwwiZuDShsWVu7nHlSOmUhc-a7MSUMe5EGSGEvnUfVVkuXztx3XIOwMJTYVGuO3fqvcVaAhRNtLkxDqcjnw6oIzRxAPRUFRwleC4L4h75mh3sDyq5nhs3_ZO9X0ZxPLdUwFhr1dbZWbKUeQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOgeItqUApjgMEtbjB4rdbLmLbBKLAkvD9NHmvWFcZ8qJvmOasjY-n1XcY0fNkzm*8wjDGTS8bst9frrc*BvoquAaZDCoPAlALXfbdlWcyWu37FbGy1DXkEGCsIMLhPbVhKK3c5KVf5RVd9MKd3CUQWDjWxSk7sy5Ki5E0c-YnKbU=">清华刘知远:写给想要填报CS/AI志愿的考生们</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">Machine Learning &amp; Data Mining(机器学习与数据挖掘)、<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>(自然<em><!--red_beg-->语言<!--red_end--></em>处理)、The Web &amp; Information ...</p>
    <div class="s-p" t="1561184295">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFt_3tpR1cD_MGm5ljX55Ax5c" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzViSEkacHRFSKCx5M6WPU9IiKMn1vwlifhlsQEmUocDHUlvTfZtFTmyhc1lIRO1PSb88B4w5eYxyCY4UtGOwNTTonJ4avsjm6jVxqWvBdRMz4ysFTJOK9RuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5Ge0ZibsJqTzd6HdTSHcydlic4TnsmpJicUrIlicD1L9ficFw/0" data-isV="1" uigs="article_account_3">新智元</a><span class="s2"><script>document.write(timeConvert('1561184295'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-51d3d22db4665618e42a785f4f3b3102">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_yBaAhGn-2TwK5Eu2jKQhjIffq3F9JLWMhUzQMnaAV-hLrL7JA_2mUEQW-_hWLaAQPllJScD3kpD8hJGZichd7Q67bwYQU0YDHdoczBsIMFB4OQFag4vcituaTT_4RV6JRmRCpXFUqwDNjfVhYjbamOdyNDjdB2VOdLaeDNczAAGX_iHL9MadA..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/JP60Os9aSE6jADM1GvzeXyAboEQJCtVCYxSO8ZM0GqPHQn7oJB3rk21ebLniaCV4RgXicWfopFIwAK1WgG9e0wpg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_yBaAhGn-2TwK5Eu2jKQhjIffq3F9JLWMhUzQMnaAV-hLrL7JA_2mUEQW-_hWLaAQPllJScD3kpD8hJGZichd7Q67bwYQU0YDHdoczBsIMFB4OQFag4vcituaTT_4RV6JRmRCpXFUqwDNjfVhYjbamOdyNDjdB2VOdLaeDNczAAGX_iHL9MadA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOjScoVKpIqL9XoMojB5kIrKu9md*FvdTF-Q9cAh4ywHT5rpb5J55Et0Knlb*AiGwJt9glTH0W*LMeL76xiYAYS7HbXN1XaTgFcR*wiiYJuma00QO3WrI99EHeu5wW4fwe67lKobm3qXvtfb7lEeoZFmM1ih3JSspU9JXnt8Sb-SY=">CFP : NLPCC 2019(First Round)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">Call for Papers (First Round): The 8th CCF International Conference on <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> and Chinese Computing(NLPCC...</p>
    <div class="s-p" t="1551235432">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFt01br_q0qJbq-5Fkgkj9lmQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzWLBS_n5-3cpozKu5m_vO3BbNOONPAIbhoJNROWs3p48xMS4mDH6jxjaNBtUGoOZAuFstbrZ_N9foQ-PPCJt8uavKBX9aclZ1FwibTfIBlf_uCUOfcYqlsmRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7icDXpYhKS43yViaicS707P4FJYIEwKykjf7aqgpCwFFRPA/0" data-isV="1" uigs="article_account_4">中国计算机学会</a><span class="s2"><script>document.write(timeConvert('1551235432'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-eb8918fe12f4ada5e06fabb6020e1442">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nZ4szzx35AthTmhNkPG1DfaB56to2Crwp-iS-wZYfc7b4m-Hqw7knZozcLSTCbtdIfXDtfFQj5IiLNutc2WGe3g0YRmYMbNeAH2kVb5j_TshgXqHL6Lt1_p535pjGOOjYg..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSJ4aAcjRgz1hHzv5icicEUiaZlE8tPColOooyDVPFbuGO9DticN2MDmiah3hY4DZgPb2Foyqrr9pYT9whA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nZ4szzx35AthTmhNkPG1DfaB56to2Crwp-iS-wZYfc7b4m-Hqw7knZozcLSTCbtdIfXDtfFQj5IiLNutc2WGe3g0YRmYMbNeAH2kVb5j_TshgXqHL6Lt1_p535pjGOOjYg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaeOM1aO3ceYknqSWbu1*1oYaDAO243CRjhpDsNLSmCKsLQdiEUb5X50ZCABfJCAWflSV8eGTpLIJ-2vCqdGu*rc3vqGJeahbCWq2zR839y0Lcpvo8At3J6NhbOqMe7arETScRQQHx8wHtsNqF9zX0LM=">BERT_Paper_Chinese_Translation: BERT论文中文翻译版</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">McDonald, and Fernando Pereira.2006.Collobert and Weston, 2008A Unified Architecture for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>Ronan ...</p>
    <div class="s-p" t="1562218248">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_5">AINLP</a><span class="s2"><script>document.write(timeConvert('1562218248'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-386c283c6313b7d8497eacac25267e5f">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9PaBqmwPGR9en_-6HIxq90yRu1S0Y1u0z4AtdVWqoWf77VwrxUADYXa2FGek4xj89dYrVCeabIF6fL7TU1JLUJ5foVpZ9WRHEfV1BN5YTzoqRySBaxEwBPuZNb0NdgBpEgBHuRXSFQ6knk0L7zU8YMdqqUPeQB69aQKpe9wbqg8he0WC6Sbi7DA..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtCJ1rmOAqUdkJUxpKD8PGsWV2SXmoOTBQOkJ4KtYtHibzXkXQLerm4NyrhZ225JKMRicsvVGnVCUOvA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9PaBqmwPGR9en_-6HIxq90yRu1S0Y1u0z4AtdVWqoWf77VwrxUADYXa2FGek4xj89dYrVCeabIF6fL7TU1JLUJ5foVpZ9WRHEfV1BN5YTzoqRySBaxEwBPuZNb0NdgBpEgBHuRXSFQ6knk0L7zU8YMdqqUPeQB69aQKpe9wbqg8he0WC6Sbi7DA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOnkoXf78xa8g15u2vWFH4JyMqrMPWhdW35yrj6iVyqWS3ERuPOVIhpVpGeokohf6DWmuP7dmtqgDhLMdqfVZmDY2Av7t2G0nQEfU9ZcG-qmt065iWPNdqR3pHdrpxjyXTIY-tmIPRptSfpVCNAzzXEdq8iazX32XyC1hiSBv4JKk=">基于PaddlePaddle的机器翻译教程 | 深度学习基础任务系列</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">for statistical machine translation[C]//Proceedings of the 2014 Conference on Empirical Methods in <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> (...</p>
    <div class="s-p" t="1559960043">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFt5XbBRNu0lfpuqkODS4ZSL8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdze01PiBNnJ4wnw9RX0O5z4LGJhI_0xaBwwjbzUwZGQaBds3McnebLy26-jJC2mTVOdno7LD0qU3tlRUV5ogrkLwCzEbTlOTidHgENlkXkLa3UqYK5Z9J9DqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6PqxX9Yx8MibJ3nial8ialvVrRs3PxhCJm7eWgR7vFrowLA/0" data-isV="1" uigs="article_account_6">量子位</a><span class="s2"><script>document.write(timeConvert('1559960043'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-04d8f5aada912c7e6cd300250336011e">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9QcArS5Int6B07gHyP3RZBo8aaNPMe1ziz6CFjwzvw6ygz0FYkexR4ux1Y-7V2Yd6Hh-tSHvruCd2B93qPlGaYISy7slts8XyjWFqbxg7zlykkaEVGXM9XK6hjPN4QW2IUUtaxBSGDCzqVWWTJjmbeHWCvD-cT9HQTmD1M-21M1FS6t2rFt2rnA..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/YjhmbbkdV6sbvaib8qM6srSVRqzuTwJUwaqMFQJtYCnKDHGP1NPMt1lHgm4KicoaWX5gjSOLaGER2P8x5fIAlpHw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9QcArS5Int6B07gHyP3RZBo8aaNPMe1ziz6CFjwzvw6ygz0FYkexR4ux1Y-7V2Yd6Hh-tSHvruCd2B93qPlGaYISy7slts8XyjWFqbxg7zlykkaEVGXM9XK6hjPN4QW2IUUtaxBSGDCzqVWWTJjmbeHWCvD-cT9HQTmD1M-21M1FS6t2rFt2rnA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOTTnb*Yy*hxgMjP8Rd*3mJ*k*g6NrHSXmLrIFGhkLBBDBmO6mmgC-HRVpB8kCwkXozqwfSiHh-JhsM9Oj6h-H9eMCQIhoFr-ZnujPBNdKfjfKpmP-MBOCC3yRBCPnswemrEkZZT-sgpG8GgSlAru4L8PdRW0NltRdjXpFhxcyxqc=">人工智能领头人邓力当选加拿大国家工程院院士!7月将出席 CCF-GAIR 2019</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">leader in artificial intelligence, machine learning, signal <em><!--red_beg-->processing<!--red_end--></em>, financial engineering, speech recognition, and <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> ...</p>
    <div class="s-p" t="1555742926">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFtxYqTCm7k4FHeT1WKMJGJXc" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzogvYeq5Y2jvxpedB4iNSnNtp7j0A-nnKMcjGeGJUiaVFuda09Q6nXTNJ1082AOXoclVzuyK-kvogwT5XSCd_LUnHNLoXaDAcpJYWe6eSKa5xu6db4Pkzr2RTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4MczoRNUr7GMvz2UheyBIia5qIicN2xsOPkajSn7EWLWGw/0" data-isV="1" uigs="article_account_7">雷锋网</a><span class="s2"><script>document.write(timeConvert('1555742926'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-2012b5d4a362827145688a6a8398c14b">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YQ_AN1HKO5msowFxqoNFwRH8ktLJk8hWbmVwDp6mq-CDSAezycbtixUUm0REK-uh8f30SZGiqy1gC5nwNF4JLT0j_lvhLLQ9M9fxyocNAAsWeGM1iNq78DSvnhSvc54szbod13mFEcEk874VgldPgTSxlxxZ7jZrptyDW-LR8J9OJBjQH7pCxQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/BnSNEaficFAaYG5QtwiagZnChaiccbr6WO7YdDLKmQ9tF3wIPMtn3nhHicUSicq2BOntQFf03iatafgcoIT2V737xFibg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YQ_AN1HKO5msowFxqoNFwRH8ktLJk8hWbmVwDp6mq-CDSAezycbtixUUm0REK-uh8f30SZGiqy1gC5nwNF4JLT0j_lvhLLQ9M9fxyocNAAsWeGM1iNq78DSvnhSvc54szbod13mFEcEk874VgldPgTSxlxxZ7jZrptyDW-LR8J9OJBjQH7pCxQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOS7Q2Y533D-uSOhTNDKqFZ9FoBg7n3nDzDcISMU6H7su38C-vUUcnZ-QslCf*bEP2bky1*9rkFxPUilyeAXjZLSGKgwO-sKqRHwe7p2QmDLdpbiTdREk5ogLafFf7zC3tPDhKtntMxXaYXX7bJMt48eioWl9I*Ik8n0bzeMthpjI=">总结机器学习优质学习文章Top50!</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">NLPhttp://nlp.seas.harvard.edu/2018/04/03/attention.html31、NLP is funhttps://medium.com/@ageitgey/<em><!--red_beg-->natural<!--red_end--></em>-<em><!--red_beg-->language<!--red_end--></em>-<em><!--red_beg-->processing<!--red_end--></em>-is-...</p>
    <div class="s-p" t="1551601969">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFt0s0lb4YYVldJ17r7KZLOKI" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz0Z4DBn4Zh0dhZ1RLwSLiLgu4t3bHnxkfGKRCJqwJ0Wxf-EelY8fdwWTnmB7Qll5B78Y3VXiaQuJ9tum8PhUhlIRGiDlm9tkBlgIE2BnNhByCCgfMeVNP-GRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7Zq0tOhrfGW6nuvYPTqOhUZxHKmopuzUG20yvzWRriaMg/0" data-isV="1" uigs="article_account_8">AI科技大本营</a><span class="s2"><script>document.write(timeConvert('1551601969'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-ff2b59070a561e1b5672a6da9f72cebc">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6ft3wfAVofsP5Peu-UiA4DFarRdcj931yH0S3dOME6VyVgrFeYQugDu5Gn9HD7GSwaBw_FZEVBVqBrMpECY3WVhqzutAOm5tOUp01q7P8Q3ehalpE2K4co-qC0X5lmgnj0CUxy9-gJezJ6ZPSkAiV5YrLfFUWGmHK9s3M9_qb4aTW33nR8dfldhkizH4pSBuPnLAu8gnutMFrS17e5WQwTCYmtwMHrWhcZrlxr9bNtvuizOBpvnHWHXe7OUbdU6dztB8_POoq0Kah8yYi34ZdxnWb8qn2FKp1iZqwg0yoRFw.&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz/UicQ7HgWiaUb35lKGb5vjrq0ePxRqAN1kZT4OhNOAPwhRhcXYhCHWkQIntAB3mvdCEic5hkeAWYWEC9GzVjlia85rA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6ft3wfAVofsP5Peu-UiA4DFarRdcj931yH0S3dOME6VyVgrFeYQugDu5Gn9HD7GSwaBw_FZEVBVqBrMpECY3WVhqzutAOm5tOUp01q7P8Q3ehalpE2K4co-qC0X5lmgnj0CUxy9-gJezJ6ZPSkAiV5YrLfFUWGmHK9s3M9_qb4aTW33nR8dfldhkizH4pSBuPnLAu8gnutMFrS17e5WQwTCYmtwMHrWhcZrlxr9bNtvuizOBpvnHWHXe7OUbdU6dztB8_POoq0Kah8yYi34ZdxnWb8qn2FKp1iZqwg0yoRFw.&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8vj5dZYOU3exZurtqeoAEORwpeeQTuJAEtcb11gUZDIkaUPQVrJIO52*6e1n2e0UTFps64alQGElzrrPjye6aH4-5MFVIAQeo6Bg6B3uT7FPc6N5VF5IQyi1pkTZxTByyVR6Ma*BJJ*ucrlJGa18Attdo4iLRC75MqGIOdKJCm-NuKHjvNBPwhCGkE5H5b7d*u7Ii4EFyoB24hgv9AHyHqD4Qatj3GIaA209zYPIb9SR6KVRiNWqOnJi0GOf9fbN51FQCd6uKsFo*VIhOc3wb5">盘点 TOP49人工智能常用 API</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">并根据语义把他们链接到基于知识的系统中.37、Free <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> Service语义分析、内容提取和<em><!--red_beg-->语言<!--red_end--></em>探测.38、...</p>
    <div class="s-p" t="1466081929">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFt_3tpR1cD_MGm5ljX55Ax5c" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzViSEkacHRFSKCx5M6WPU9IiKMn1vwlifhlsQEmUocDHUlvTfZtFTmyhc1lIRO1PSb88B4w5eYxyCY4UtGOwNTTonJ4avsjm6jVxqWvBdRMz4ysFTJOK9RuO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5Ge0ZibsJqTzd6HdTSHcydlic4TnsmpJicUrIlicD1L9ficFw/0" data-isV="1" uigs="article_account_9">新智元</a><span class="s2"><script>document.write(timeConvert('1466081929'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=7&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			
    				<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a>
    				
    					<b style="float:left;font-weight:normal;margin-right:10px">...</b>
    				<a id="sogou_page_4" href="?query=natural+language+processing&type=2&page=4&ie=utf8" uigs="page_4">4</a><a id="sogou_page_5" href="?query=natural+language+processing&type=2&page=5&ie=utf8" uigs="page_5">5</a><a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><span>8</span><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=9&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约450条结果<!--resultbarnum:450--></div>
    </div>
        
    </div>
    
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "null_70-null_71-null_72-null_73-null_74-null_75-null_76-null_77-null_78-null_79-";
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
    <!--1562763693560-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "99eb8cd1-e31f-420e-924d-f5d9c73ef20e";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693711;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693711",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "99eb8cd1-e31f-420e-924d-f5d9c73ef20e",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A5372153E42F2E67",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "9"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-34dfc9557cc1320b49aa3d167e7ac47e">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_7fQGjTyIL-1NE2rdpSHNT_PqMYppWWo_gqRlKfmDQA6nFj5HwsoxgtTIinTxh90IKzcaVGrVrE7iHquxZiERbGNUFao6ceZ7BWD7BXFEgVc9xuWlUQwUI5lH4yz8r8sL_oLok1RP7z76RehaZx3_X4UpWrzOIiKnr-HtxEtXiJflztgI7RZ1g..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/wc7YNPm3YxW1e3RCeE05KIE4QEoAJUgn3iaBcAvakASPUdAw2YeMOnCMic6eH4gklOnd8ll5dkiboQOWShTkF1tEg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_7fQGjTyIL-1NE2rdpSHNT_PqMYppWWo_gqRlKfmDQA6nFj5HwsoxgtTIinTxh90IKzcaVGrVrE7iHquxZiERbGNUFao6ceZ7BWD7BXFEgVc9xuWlUQwUI5lH4yz8r8sL_oLok1RP7z76RehaZx3_X4UpWrzOIiKnr-HtxEtXiJflztgI7RZ1g..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOPIeYvRrU8tOjcQw5HVzO0sE9PjWSt5S5lzLLBMuVUNNMY1q2*VI6tAaIQTkaxqYldvhd-yOTH0d3ITjSVPQElc31qTAvyxTz5-DlAmKdXLP6qvNZ1PGv4I3qsZhCrYkiIrEtdY2hZs1olyZLWkBsZpzOrtvPv6ZEVD5R8PQPdKc=">清华刘知远:写给正在填报志愿并对CS/AI感兴趣的考生们</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">Machine Learning &amp; Data Mining(机器学习与数据挖掘)、<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>(自然<em><!--red_beg-->语言<!--red_end--></em>处理)、The Web &amp; Information ...</p>
    <div class="s-p" t="1561355499">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFt58NVJTkYWvPtICKgg8ka60" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzf7q-LFYKNmAkybERv2CNLE2OnEU4l-_vT6xHI0zQ6IKCKuVey7IE3VeEtijCirP7kFqwXqB53Pa3Tc2dOPv3QalnFw5igmO6M2YHelytzGC7U6eEQ8GXSm4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM46WJlQ8GYRWPhThl25rSKJEYBm408fnEkYS9DUkiaSxGg/0" data-isV="1" uigs="article_account_0">大数据文摘</a><span class="s2"><script>document.write(timeConvert('1561355499'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-68a10dc747659561b1ebb7020ada35f6">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9gketO8GYP-KkB2LR8-0Mf8RVB6HvyWNYYvlL721TDYC8HAEho8fAd9Spz4z_fdOyVrMkHx_7a1CZdo692aJGMaE5kZrsVE_TGaiuW4OIzpIk0tPRgRR3NKjWoRbBLbemOfkkgZMvFlH0UVu7pMg-GO4GzvQ7rz0xcsGevQpmGi3P28temKTOwg..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/ldSjzkNDxlkdfvKiccNMt24a7pFQn07dtoYnfl0juJDzNX9yBs1kIs9IOFpgMV1mJMvPEOoHOYia48kCv5O6fCoA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9gketO8GYP-KkB2LR8-0Mf8RVB6HvyWNYYvlL721TDYC8HAEho8fAd9Spz4z_fdOyVrMkHx_7a1CZdo692aJGMaE5kZrsVE_TGaiuW4OIzpIk0tPRgRR3NKjWoRbBLbemOfkkgZMvFlH0UVu7pMg-GO4GzvQ7rz0xcsGevQpmGi3P28temKTOwg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOvN0ZqKjCxyEEvYE-4QS-iOytDxIzJAW9WYLRc0T6NDlUIQdgt7gBPNmJjgxCNUSfwgwGomZCEhYlKCzRt3ZezF6E3pTt*zpkDKcNZB5nTvIu0x6KKJmY9rf6U9LCU6S*1g6pzQI5B5D6yuYZvOhliq6vxQz0NoHhiSrYXtiUvJA=">50 个超实用的机器学习API,拿好不谢!</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">地址:https://www.diffbot.com/dev/docs/analyze/Free <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> Service:提供包括情感分析、内容提取和<em><!--red_beg-->语言<!--red_end--></em>检测...</p>
    <div class="s-p" t="1562164368">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFt9_Zfx05o6tp-_qoIlkxFSA" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_f66TzA82SkrJIXMM3R5FcfO15v_2fapQ9N2i0GKD2AUiAPLgxjfvn1St8oCa3N_rbFmbeyACz0TXIhUnFa8TtEeWi-E31q48QTgXsFjpxpwDF7aZQTT6W4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4VxFL2ib7A41YaoXxx0E3kzr2XhQOkuAKCibuiaLBicmFcgg/0" data-isV="1" uigs="article_account_1">优达学城Udacity</a><span class="s2"><script>document.write(timeConvert('1562164368'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-8994296a7989e22fde94d431259bce7e">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nfDln-3xszuoeaT6CVWlI_NdG2DRSXR8nNeMUYaQKuSqGGVckVK6y9QD9xP1RHwzzUgt3F257y6C5j2AEcz7yfKgRIG2hutclMe1IyXGA5oZ4BxQN3BwMyPP28temKTOwg..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSJddGaDWnVUC6nGYfW0SjyD1IL5GWClD5fmydWnicw8pansryaHqdLSCbwHRlPu3OIBTcbkoCX5TQQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nfDln-3xszuoeaT6CVWlI_NdG2DRSXR8nNeMUYaQKuSqGGVckVK6y9QD9xP1RHwzzUgt3F257y6C5j2AEcz7yfKgRIG2hutclMe1IyXGA5oZ4BxQN3BwMyPP28temKTOwg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaffGF4UDvac7JhL7P1HbVIg*2ctVMGeQYOqh9uftr5dG42yT-4ut*2kNdPEOXBf822DJ5QJ1MI*Rxqj-vGXH-0WpyqBXWlVtD224XtcYLPw3fPB6gL3IjZgdk3KsTV0paR*mDEXvJIAvs5xJ78IRZ*g=">一文读懂命名实体识别</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2"># 对英文进行实体识别eng_model = StanfordCoreNLP(r'stanford-corenlp-full-2018-02-27')s_eng = 'I love <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em> ...</p>
    <div class="s-p" t="1555997404">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_2">AINLP</a><span class="s2"><script>document.write(timeConvert('1555997404'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-54929978c2995f7fe44c579ca1452213">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nflPxvA52fTOumg7N528muTE0Tq9-ci3BdoOiIepLE4eZ0kyCr1ccHIYH_a_kgetRbQcdMU5sLPo0EmdumL4hJIdHL4bgD8h_ubdYygRHqavByUfEFcViPXdrgozfSg6bw..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSIJJK0yg6y4hP6eEcUnjhyOz7WD0JIMhianmN0ib4jD0aE2XxCq5j1RYBcVyAaj2dB4yeJEnHsyaB9Q/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nflPxvA52fTOumg7N528muTE0Tq9-ci3BdoOiIepLE4eZ0kyCr1ccHIYH_a_kgetRbQcdMU5sLPo0EmdumL4hJIdHL4bgD8h_ubdYygRHqavByUfEFcViPXdrgozfSg6bw..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaffGF4UDvac7JhL7P1HbVIhq5JKudMNfxWqwkN9kVTEbX4Myc8oeD1miL4c9HJ-AsS8ew2OvjeP*YtUbHGb8DAw-lkK5Ul0PMqqewZWOYb8fDdeXEwPSCcbGLSlJ0ycOoWo93VVA97AQ7nSxxo1Mlhs=">一起来看看词性标注</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">eng_model = StanfordCoreNLP(r'stanford-corenlp-full-2018-02-27')s_eng = 'I love <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em> technology!'word_pos_...</p>
    <div class="s-p" t="1554789314">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_3">AINLP</a><span class="s2"><script>document.write(timeConvert('1554789314'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-90f2e9e44f1804bc946be660db3730c8">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9zob_GJSfqXs1W20enfB-CCRpppg1INJ2RgmrnZiAymlsxGwOaSdNFdmZpYNdwlwG4G_wnqmBCbQAIWx5txkt357y5i34q7lMwD0tF801HxsG-JVPVdGzUMwrGBr3tXz9OU_yeolkePT9yk-w91iOj4X_x51x0YJi1sByrrGnV4hhlgeRt7bSzA..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/ibaXaPIy7jV1dQbiaLCUO8Qy4QIRxibIiaKQsJkdGlD8mBjbY7wia7Wzk9F1zibfCHBamYeUTmmbltvSUDJ06z4SU2LQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9zob_GJSfqXs1W20enfB-CCRpppg1INJ2RgmrnZiAymlsxGwOaSdNFdmZpYNdwlwG4G_wnqmBCbQAIWx5txkt357y5i34q7lMwD0tF801HxsG-JVPVdGzUMwrGBr3tXz9OU_yeolkePT9yk-w91iOj4X_x51x0YJi1sByrrGnV4hhlgeRt7bSzA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOqZoMUpAtKgbb5Nk3WZXH87SHQnLGJzwCyyiqaV3PleID5b9vWIhEOLA4oBaWYn39FtXYcNa-kh*IzWCTwxAYx*IHRhiKP3*ZgrcGXAmjbbdkNNmZiNgr4sQkK-W27AoYk5OMR4kpo3UEBA4O-aaXHBH-q9JZlPaMQj8czT96YUs=">书单 | 想成为一名合格的NLPer,应该读哪些书?</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">https://web.stanford.edu/~jurafsky/slp3/统计自然<em><!--red_beg-->语言<!--red_end--></em>处理的基础Foundations of Statistical <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>作者:...</p>
    <div class="s-p" t="1559175736">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFtx8-WU9u-tdYbETTzZGm-xo" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz7bi_4TxS4yM3ko2T8dyafz-GqN-js8f8DSv0kjL1x4-c8oxUzJs3yZm9nas5NX-xfzUUtwy-gj556KrceFV14G0OsccV_84GRVR_EXPTn5vB-DzcMJgIj6UiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7JT1FAEQN32XrRB5ickep43amP1ibbDffMv0cQHcFezlzw/0" data-isV="1" uigs="article_account_4">将门创投</a><span class="s2"><script>document.write(timeConvert('1559175736'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-08a339e62efe4155b7153eed0b251f7a">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU6195PJfGHgH4vzKq__UAbr1e_7BHEPN6Pn8_12FgXYhSnW3BL4020luR0GvpLHPm3g7A9CsfZMiDHzxRrTZGiwWxVmiNY5gNe7UBGOuZxndvDFe7G8dqcnG5rvzHZXxeLdyg..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AefvpgiaIPw3t7LdibCnN9tQJ4DwbJX0XoniaFIa3jalqdkGr82RwjcaFU1vz4FRJh6HcAs1FRQju4mzaf0oNUpIA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU6195PJfGHgH4vzKq__UAbr1e_7BHEPN6Pn8_12FgXYhSnW3BL4020luR0GvpLHPm3g7A9CsfZMiDHzxRrTZGiwWxVmiNY5gNe7UBGOuZxndvDFe7G8dqcnG5rvzHZXxeLdyg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOfx8Jfwfb0qSMYPxNYhbrgS3CozazEQZxAv0VNIHKFwaiaMiwXYFYcOWI1W6UR0akeeHxpPcxgW1xRulhVpe3pkyK5STQXuB8lR1cYCOrd3-LW3N7cO8fEEdUoCT1W00CRf-uczCsHsJYkABnhXLNSMeLs8YFcrFI*nGA1oKnr68=">移动端机器学习资源合集</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">formsText Recognition and Translation on iOS Using ML Kit and Google TranslateIntroduction to <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> in ...</p>
    <div class="s-p" t="1555822026">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt76uwDKxyiHVKwWo3xeOGlQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzOmfPGPvs25f63z-PZUbG8HxQJWHLEey2lB_Az_B87nOJKBnIhqiDW7MGTbU99d_IxbqfApI7PH6BhddYaTtWZ7hwmGFwNQ87y_bdZbkQO_tbR99V7P4u1eO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7iathEPUfgnAWr4Hml9INphvANAFNW2LkrRd5RxBqiauzA/0" data-isV="0" uigs="article_account_5">专知</a><span class="s2"><script>document.write(timeConvert('1555822026'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-c4f5ca2f5bf33ff4b71ab97ebbfe90c0">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nXtKn9JmYtU4ro3oGQ_ATMUnimdIEt72jRD6ZNZqHAGqt9HGA9DYiuOjBkzflzpo42EnykI9AkxMJQQ7-F9EUjLY-4Z0VOVpfCXrpYqDstoNa8OEjWI0iLlj32-j2KiwUw..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSK6Zs4BPCqoEwYicmD3MYyAV1dAk3ILtvib1a6LlxNJjRiaqqK4XqdIqHegvyslMLkgbpWC2felS2EXQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nXtKn9JmYtU4ro3oGQ_ATMUnimdIEt72jRD6ZNZqHAGqt9HGA9DYiuOjBkzflzpo42EnykI9AkxMJQQ7-F9EUjLY-4Z0VOVpfCXrpYqDstoNa8OEjWI0iLlj32-j2KiwUw..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaeOM1aO3ceYknqSWbu1*1oa9tumwowQ-VlbBj4UUJtInhNJVHfzDyzqAKkdLRAmY7rZwkQ*VRElmJjnaQ3H*tcRIJbOBqt4RGNTITcOLcf2mpuhG7HNKkm3CozqgkPtDv6KIrzFIcdVMJ2IJlUn5vu0=">BERT/注意力机制/Transformer/迁移学习NLP资源大列表:awesome-bert-nlp</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">Learning in NLP This repository contains a hand-curated of great machine (deep) learning resources for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> ...</p>
    <div class="s-p" t="1560042621">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_6">AINLP</a><span class="s2"><script>document.write(timeConvert('1560042621'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-9317eb5cf92d80dd57a124cecaa8919e">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9C2aEahQZsqDBQ7Jbb8P4h_HZiDYc_M7RNc136j4pdyAYlH_IoeeoxYsY8mc1-tGE9P9vG9MpP2zNdG6SEfI5NvgxOxUSOC-JfW-9mvdopLrxevcUBpsQkrhL_trChZ9oE8PVDZhksCNizdd8bj8_JnbLKWauCyhnOPUdnmXR9tjYl_Q5RRZQjg..&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_png/tN1blB6ujNX5IGEia5vAanI8xQ7adnCzeia5G2wxYYqicQl5hJvoicwDt1BqmnAUGzuU55zm60DTmxictbXwEfnGO2g/0?wx_fmt=png" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9C2aEahQZsqDBQ7Jbb8P4h_HZiDYc_M7RNc136j4pdyAYlH_IoeeoxYsY8mc1-tGE9P9vG9MpP2zNdG6SEfI5NvgxOxUSOC-JfW-9mvdopLrxevcUBpsQkrhL_trChZ9oE8PVDZhksCNizdd8bj8_JnbLKWauCyhnOPUdnmXR9tjYl_Q5RRZQjg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAO2ttIy*Zdal7bAZ7Rofrwse*Z5A3gZeuVM5tV1XGAomCC6JW2*bfhWpJysEKffDTceGDitsuwJtwMwMRLz3MVvNrByXdPgzCxS01I9CvDMoBiAUgthdDrDXK1a9eokSRW9uxZhSp99K3WD92dHR-RUA56-YZOPXf8Te8P7FMyWIs=">想要快速成为数据分析师,最最最需要掌握的技能是?(附20G数据福利)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">and Machine Learning》 6 数据挖掘教材当然,带你巩固知识的数据挖掘教材一定是有的NLP 经典《<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> with...</p>
    <div class="s-p" t="1496881743">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt6WkhlNdX-4sXjKtgbdk8lA" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzQp-92tKjUV35ztIj98EYAUx31OY5nQfzHWrepImBB4lTLnfcQyAayidOKdnAw2Lnh0IKdz5iyI1aVVX9uDNZtCFAOqWxw3tPxo2lmrV6CShiYfKK0QLLlGRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM68hDKW7fcDMUKuicgtAD4ia2AHibO2EL8Q3Ea7LcU9WBNIQ/0" data-isV="1" uigs="article_account_7">UniCareer</a><span class="s2"><script>document.write(timeConvert('1496881743'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-630554e1465a1e480d50dddbfa6760dd">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9Cu_jcA_WxHnhGsE6_BAq3o5JU1mF7ZiNfZsIOacBiLVYK1qNDW5tWWjdONlwsEJc7DC2YynfqVmp81hx6nK9Tek9kAaqnSd73-SvjJY0azxxT29VH_PMbuJnXgqjEj8_kbemI0KSjsno3DeDqkCKHfrTURwXcrt0tHk2hD03FJvyPfCoem7FzA..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_png/HZPqXI3AVTlOXOlHr5Met3NwPjy0PlZxFeKh98jTgfmXea1MMbaByAzpricmlTM9xibbfphxDrt4HNYJQj6XaFug/0?wx_fmt=png" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9Cu_jcA_WxHnhGsE6_BAq3o5JU1mF7ZiNfZsIOacBiLVYK1qNDW5tWWjdONlwsEJc7DC2YynfqVmp81hx6nK9Tek9kAaqnSd73-SvjJY0azxxT29VH_PMbuJnXgqjEj8_kbemI0KSjsno3DeDqkCKHfrTURwXcrt0tHk2hD03FJvyPfCoem7FzA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOSqymWlk8eMpjsFVtmIiaGGN-6MLoU4Cymqo0-PABHi5krzYiI592ZMpp6Lyh-sqMFpetf*1BfnCk6Ur07Abrg4kJrLaipwb5m75sTlOiVhvXcc3nix38H7a184DVhXS3*jHUOJkAGGOim7Ulcg0r-uNoW4JapXhT2qEffqeuXQY=">期刊动态| Register Studies创刊号 2019年第一期目录及摘要(语域研究各个流派纵览)</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">He applies his expertise in computational linguistics and machine learning to a variety of problems in <em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>. ...</p>
    <div class="s-p" t="1557763207">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFtz_P8yjUDr05kQoAjFCs06Q" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzHu8y-f4xNxbMn15PGHqPSEaFvUj2BNq-R-pxoHgx86s7pEaGndXAN_X1Mr_HWhI95PE1DvSo26rnSgvvt39aNwhDwVpU_Nvm1A7XUia0jrrlcavUidvw1qUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM6ic7eHJVDEoBD9W3DYV53JCCbGg2CcxoLgcgeBQZ3PL5w/0" data-isV="0" uigs="article_account_8">语言学通讯</a><span class="s2"><script>document.write(timeConvert('1557763207'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-c5220e2ccac6931cbdeb6cd143a6e5e9">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9CW9FzPW_cTve0BGCki2oJZvhKUj8CY_uOIlsHq2DLzzru_O5GpPsqAMKORk8rMS9yInKQykSpgZt50xLF7gmc2r5FSAZchUDl0p92_0OUNeO9VVYACC6YLh7XGhEEaHKAzZkmtMw9JpdFrgPJJ9-vrR2R5fkbdSE-WIaQiKztlbwdVqCwyPdzA..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/42N1g4fYAajAfkuIcoCRLCI878w5054lYbEFNZY4fbRtScHM8Z0hSQYJNmBibvSpgG8p9iamTjianu1fkRwdI8VxQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9CW9FzPW_cTve0BGCki2oJZvhKUj8CY_uOIlsHq2DLzzru_O5GpPsqAMKORk8rMS9yInKQykSpgZt50xLF7gmc2r5FSAZchUDl0p92_0OUNeO9VVYACC6YLh7XGhEEaHKAzZkmtMw9JpdFrgPJJ9-vrR2R5fkbdSE-WIaQiKztlbwdVqCwyPdzA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOSuWHK5eGKbMcqT6HRkCmtFG4aXldXBAmgtDor2o9RdUflLox3Jsr*TyVOHQjO1doEAeLncifJ6lx6r9vZ5465O-wJjjgPrpxRV0ao9dhUGgvp*auwuFN85OnY8t*36JR*KbUvTmsE8zdL9hdFvIiieL8V-kl48akmVcBkrpDVPQ=">拿起Python,防御特朗普的Twitter!</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">https://medium.com/google-cloud/comparing-tweets-about-trump-hillary-with-<em><!--red_beg-->natural<!--red_end--></em>-<em><!--red_beg-->language<!--red_end--></em>-<em><!--red_beg-->processing<!--red_end--></em>-a0064e949666以上是完整的...</p>
    <div class="s-p" t="1557162745">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFtz2R9cB05jXT4OE7nIbhxpk" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzhWKZ_fCt6SpR4idcUnmBW4WzCtCxRrneJ3lD-kxl6pDFnZhu1SQau3HGoiAQk4BRC0DP2ocxbpYb1xIAnQ0PEYQi4VjTHYOYoJn8_vXOR5VpDuz4zz_Hq24OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM432VCMNLhPkTALiciajUZOEX8b3QckDy6RZjBxCoPOJYdQ/0" data-isV="0" uigs="article_account_9">量化投资与机器学习</a><span class="s2"><script>document.write(timeConvert('1557162745'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=8&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			
    				<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a>
    				
    					<b style="float:left;font-weight:normal;margin-right:10px">...</b>
    				<a id="sogou_page_5" href="?query=natural+language+processing&type=2&page=5&ie=utf8" uigs="page_5">5</a><a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><span>9</span><a id="sogou_page_10" href="?query=natural+language+processing&type=2&page=10&ie=utf8" uigs="page_10">10</a>
    			<a id="sogou_next" href="?query=natural+language+processing&type=2&page=10&ie=utf8" class="np" uigs="page_next">下一页</a>
    		
    		<div class="mun">找到约450条结果<!--resultbarnum:450--></div>
    </div>
        
    </div>
    
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "null_80-null_81-null_82-null_83-null_84-null_85-null_86-null_87-null_88-null_89-";
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
    <!--1562763693710-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "05013680-fa44-45c4-ab03-7194f620ce62";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693798;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693798",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "05013680-fa44-45c4-ab03-7194f620ce62",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "null",
                "exp_id_list"   : "null",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A53613C3E42F2E09",
                "rn"            : 1,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "10"
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
    		<li id="sogou_vr_11002601_box_0" d="ab735a258a90e8e1-6bee54fcbd896b2a-8ef7dff4d122e71ade2030eb47310543">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9W_5a9oarm54ku1BmSTbX_7i5ujqO_a-jZOXoX0RMq57md0nqddVq9dzFMteUEpKoBxw1cozEUP1IsDTg0nQfizFqBZZwXwuA1SnjPuhMoQ1wOrMfba5-SKkBT4jGQSkJ_g6UxQGVO-nuoRzVMZb6U8ls2M-CFFPVdLcocKV-dkP1AfaFW2DefQ..&amp;type=2&amp;query=natural language processing" uigs="article_image_0"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/PPmNUrRwibGGAIvCR88olkVsdKF5ibxO78LDw1vMpXfmG1g5LhEpkIAzE8DJyeTbC2SibCog0h5hCugOLHwcWr0QQ/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9W_5a9oarm54ku1BmSTbX_7i5ujqO_a-jZOXoX0RMq57md0nqddVq9dzFMteUEpKoBxw1cozEUP1IsDTg0nQfizFqBZZwXwuA1SnjPuhMoQ1wOrMfba5-SKkBT4jGQSkJ_g6UxQGVO-nuoRzVMZb6U8ls2M-CFFPVdLcocKV-dkP1AfaFW2DefQ..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_0" uigs="article_title_0" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOdakoXHaCO*P3*uwFhZvE7e8ivhD2klGWfqknbG6XOCPFl7UQ1ZuqvNBU6P1uJ7PuSDs7v3LWrC5tOdC3vzpqfl3DACfqrWYi*agrVIM2qRfkD6EDTMbr-90ILG7BczIUgcCcU*yMFZin3PmrR5N-*azNQRDHPgj3un5I88YlsBM=">干货 | 适合NLP初学者的8个免费资源分享</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_0">二、自然<em><!--red_beg-->语言<!--red_end--></em>处理&mdash;&mdash;微软 格式:课程课程地址:https://www.edx.org/course/<em><!--red_beg-->natural<!--red_end--></em>-<em><!--red_beg-->language<!--red_end--></em>-<em><!--red_beg-->processing<!--red_end--></em>-nlp-3 简介:这是一个自学...</p>
    <div class="s-p" t="1562110842">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_0" i="oIWsFtxaKT5QLDVKizLoRbwwVYTQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzkfvkhxKMhf3wC1umPyQItledchy2KY-fSnj3-QSEMvm464ON5Mzz0e0TcrVsZELVMIOL347gGWPfRu9fzA3Nmq_UNfY1335GfleJxBLs7rgB96IQ2YR7NeO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4nvovl4Ic7qIkM0HpQWebz57b9JOcJWuTxOKqszvaXXg/0" data-isV="0" uigs="article_account_0">THU数据派</a><span class="s2"><script>document.write(timeConvert('1562110842'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_0"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_0"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_1" d="ab735a258a90e8e1-6bee54fcbd896b2a-2f9552c5266d589e24c632f8670a9b3a">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_1" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nUoIJbO3l16vaHd2AJqKh9kSjMVJQ1EcOk0ufnxmYbfp3HT8AsZbKihWeG0-IzcHsso0PgY3XZsFrysCtpWZuQF63m94BfboPHYK6IMjEYTYhvd5qklkuZeFW6cwuUnkdA..&amp;type=2&amp;query=natural language processing" uigs="article_image_1"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSIvEY3K9QoxRz1Nic7XVXXibonmnkOmfNEToPaStaGXQSMWicqGbW80Y1viacEDQ9epOJXJC5a8QNfBUw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nUoIJbO3l16vaHd2AJqKh9kSjMVJQ1EcOk0ufnxmYbfp3HT8AsZbKihWeG0-IzcHsso0PgY3XZsFrysCtpWZuQF63m94BfboPHYK6IMjEYTYhvd5qklkuZeFW6cwuUnkdA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_1" uigs="article_title_1" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaffGF4UDvac7JhL7P1HbVIgTiSZs*M92-9ASJwNhblZrXIRf14TqXMgq628Lw3FztKcHNSxUlANddGtnS5qLWqvLPPKMQ8QzZVN8*Nwwn0nOIGKaZ9KNpSM5s-dshNFN82rzzTuZGKpcRZSG*6qNemQ=">NLP研究入门之道:走近NLP学术界</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_1">介绍国际学术组织和学术会议的组织形式,以及国际学术论文的查找方式.自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,NLP)在很大...</p>
    <div class="s-p" t="1559093443">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_1" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_1">AINLP</a><span class="s2"><script>document.write(timeConvert('1559093443'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_1"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_1"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_2" d="ab735a258a90e8e1-6bee54fcbd896b2a-2714ee9e547d3eec0fafa0dacaec5d83">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_2" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_7fQGjTyIL-1NE2rdpSHNT_PqMYppWWo_gqRlKfmDQA6nFj5HwsoxgFeedKZJk_LzRd4K0X4gZ9WHQdKy3iPeEzNAFkBrgZY59ae31qTIjPUlBrwtbRxLG3ahe0CDtQR4iYWlAbMVU_agiCweFHjwRROwPsYuk9kL06fuyy6J8Zf_71bqkOtiw..&amp;type=2&amp;query=natural language processing" uigs="article_image_2"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/wc7YNPm3YxXU9toK7fnL4HxvE0hl3fterZnNIEVPBicZFr61nsVTDVechCIhliciaj6SEOZlKEV1kUh1d7JIpAZhw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9_7fQGjTyIL-1NE2rdpSHNT_PqMYppWWo_gqRlKfmDQA6nFj5HwsoxgFeedKZJk_LzRd4K0X4gZ9WHQdKy3iPeEzNAFkBrgZY59ae31qTIjPUlBrwtbRxLG3ahe0CDtQR4iYWlAbMVU_agiCweFHjwRROwPsYuk9kL06fuyy6J8Zf_71bqkOtiw..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_2" uigs="article_title_2" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOPIeYvRrU8tOjcQw5HVzO0icD3YlsAXR5*t0Xt9-2XnxKk2OZ2LYLnH2kooa5JoAbxT9jpjbnQQq1*TbvrZ2NPS5x4h1A6EYDdEq0xcc6Og72M0HUnwCjQJh9QB7mMyo4V5Bo9rjhVHGL*7-kxJPCI1Jog1cttlFjS4fQhsOItoU=">专栏 | 微软研究院:NLP将迎来黄金十年</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_2">比尔&middot;盖茨曾说过,&ldquo;<em><!--red_beg-->语言<!--red_end--></em>理解是人工智能皇冠上的明珠&rdquo;.自然<em><!--red_beg-->语言<!--red_end--></em>处理(NLP,<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>)的进步将会推动人工...</p>
    <div class="s-p" t="1543724556">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_2" i="oIWsFt58NVJTkYWvPtICKgg8ka60" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzf7q-LFYKNmAkybERv2CNLE2OnEU4l-_vT6xHI0zQ6IKCKuVey7IE3VeEtijCirP7kFqwXqB53Pa3Tc2dOPv3QalnFw5igmO6M2YHelytzGC7U6eEQ8GXSm4OZCnxixtX&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM46WJlQ8GYRWPhThl25rSKJEYBm408fnEkYS9DUkiaSxGg/0" data-isV="1" uigs="article_account_2">大数据文摘</a><span class="s2"><script>document.write(timeConvert('1543724556'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_2"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_2"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_3" d="ab735a258a90e8e1-6bee54fcbd896b2a-9f54fb646589a740f53a95e77808f963">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_3" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9QcArS5Int6B07gHyP3RZBo8aaNPMe1ziz6CFjwzvw6ygz0FYkexR4pjKDza8ruKaa_MgYoBY3v9qAU9GF8hCpjLjwDFOep2jFwqgVtDpzoV9E-qXyWvIsgd78qAtd32cVGunTKcjLLRrCdWsGl9JpNUNBDoUXgQdVyFDQDC3-RLuL0unUdKkuw..&amp;type=2&amp;query=natural language processing" uigs="article_image_3"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/YjhmbbkdV6vm0jpKzzT8dIaYxY9GialUl3Sf7W3sYK8dDRrWD6ZP3hr2JRI7wnfWeibiacL9sGhSmefPzBHoGyoibg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9QcArS5Int6B07gHyP3RZBo8aaNPMe1ziz6CFjwzvw6ygz0FYkexR4pjKDza8ruKaa_MgYoBY3v9qAU9GF8hCpjLjwDFOep2jFwqgVtDpzoV9E-qXyWvIsgd78qAtd32cVGunTKcjLLRrCdWsGl9JpNUNBDoUXgQdVyFDQDC3-RLuL0unUdKkuw..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_3" uigs="article_title_3" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOTTnb*Yy*hxgMjP8Rd*3mJzNXr3DvROoRotB7OdaQOjRqsb-zFqW8JigrquCuy5rvp*2kueCIDbxVtl*PGuqTRM-BeSNYm*uSj-dB97Z59fTWkQuPatw*sQRiT5bk0gqXgTX7m5CwR*3H*DZbv7viqoLe0D-vztpiuCTFWYUgERo=">科技部回应基因编辑婴儿事件;华为确认自研操作系统替代Android;网传明日启动携号转网新流程丨雷锋早报</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_3">该系统在自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>,NLP)领域实现了突破,在性能大幅提升的同时,实现了多语种的支持,并解决...</p>
    <div class="s-p" t="1543535810">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_3" i="oIWsFtxYqTCm7k4FHeT1WKMJGJXc" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzogvYeq5Y2jvxpedB4iNSnNtp7j0A-nnKMcjGeGJUiaVFuda09Q6nXTNJ1082AOXoclVzuyK-kvogwT5XSCd_LUnHNLoXaDAcpJYWe6eSKa5xu6db4Pkzr2RTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM4MczoRNUr7GMvz2UheyBIia5qIicN2xsOPkajSn7EWLWGw/0" data-isV="1" uigs="article_account_3">雷锋网</a><span class="s2"><script>document.write(timeConvert('1543535810'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_3"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_3"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_4" d="ab735a258a90e8e1-6bee54fcbd896b2a-76e66fae225ca8ad613e28ed002731d0">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_4" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5ne7Qwmxwpzq_g8Ks5l7XXya4MqqeZN0z1ZSjdXfW9w9fBqdNpDIb35hXG1MdlQRCvlYivQbGXJkZ0O1p-gvgEvg06VlnDjG-Cz0TRY4q97FF4ysyz_MjiwjYl_Q5RRZQjg..&amp;type=2&amp;query=natural language processing" uigs="article_image_4"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSKWXwubuYytMyHfAozUsOpd3kyzicy8dHdPCYia7Tzrich5LoFmRjIT4prRgib6ar0iaHuCTRGh1zXibo1w/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5ne7Qwmxwpzq_g8Ks5l7XXya4MqqeZN0z1ZSjdXfW9w9fBqdNpDIb35hXG1MdlQRCvlYivQbGXJkZ0O1p-gvgEvg06VlnDjG-Cz0TRY4q97FF4ysyz_MjiwjYl_Q5RRZQjg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_4" uigs="article_title_4" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaffGF4UDvac7JhL7P1HbVIj4uozC*7PNRgWovyvkzgc3jAirZGgIwdXsouqBQcJL349iD5nH34eMd3GBOYirsa2oPSVqpsirLXmC5f*i1bzSSoJO4haL5oU52ccWhKs7KzqipRk7neme6kar6YRNVwM=">上百种预训练中文词向量:Chinese-Word-Vectors</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_4">Intrinsic and Extrinsic Evaluations of Word Embeddings. Chinese Computational Linguistics and <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> Based ...</p>
    <div class="s-p" t="1551160212">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_4" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_4">AINLP</a><span class="s2"><script>document.write(timeConvert('1551160212'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_4"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_4"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_5" d="ab735a258a90e8e1-6bee54fcbd896b2a-dfd1b86ca1ecec9971075c5d6aa1abfd">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_5" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YQ_AN1HKO5msowFxqoNFwRH8ktLJk8hWbmVwDp6mq-CDSAezycbti5dTtF0FXTl3egmFFIqiRkLA5Sqq1TMulhcdigEPtXCKzO2a4XJxtJo0o0q4MLsZBdA51LWwy1LlZpWYQClipgLFICVz5fvQzvi6ExpG5vXjJm438bIHWZtFH6In5Ei3zg..&amp;type=2&amp;query=natural language processing" uigs="article_image_5"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/BnSNEaficFAYcUH9kM0Sl5ibMZc1r14GUicrJYoz0IMaZ1qsDkxuHaCC33A7UALRHtQPiajXXMuSAKH2hYgZWHdicCg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YQ_AN1HKO5msowFxqoNFwRH8ktLJk8hWbmVwDp6mq-CDSAezycbti5dTtF0FXTl3egmFFIqiRkLA5Sqq1TMulhcdigEPtXCKzO2a4XJxtJo0o0q4MLsZBdA51LWwy1LlZpWYQClipgLFICVz5fvQzvi6ExpG5vXjJm438bIHWZtFH6In5Ei3zg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_5" uigs="article_title_5" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOS7Q2Y533D-uSOhTNDKqFZ8JM9K2cHsJDRD6tsL35s8EDd38MAhSWmucidTmr1k5cLzTfcpxDw77raGfTypILXykaWh2BSB-DJ7wEl-M8ErO6CUzaGAsQIRtUjkW3Zg7I8NUcxyYeAwLkhb2CudTv7RLDFaPsCRlmetPt5Mhzae0=">清华人工智能研究院成立,张钹姚期智分别任院长和主任</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_5">在AI 方向中又分为 Artificial intelligence、Computer vision、Maching learning &amp; data mining、<em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>、The Web ...</p>
    <div class="s-p" t="1530179478">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_5" i="oIWsFt0s0lb4YYVldJ17r7KZLOKI" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz0Z4DBn4Zh0dhZ1RLwSLiLgu4t3bHnxkfGKRCJqwJ0Wxf-EelY8fdwWTnmB7Qll5B78Y3VXiaQuJ9tum8PhUhlIRGiDlm9tkBlgIE2BnNhByCCgfMeVNP-GRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7Zq0tOhrfGW6nuvYPTqOhUZxHKmopuzUG20yvzWRriaMg/0" data-isV="1" uigs="article_account_5">AI科技大本营</a><span class="s2"><script>document.write(timeConvert('1530179478'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_5"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_5"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_6" d="ab735a258a90e8e1-6bee54fcbd896b2a-8a609b6121c13a54e5d271a578e0cf66">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_6" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU6194x6bk_fD1tYCdRqGRp4ZG1T6e-chBfqS1iQfLGM4yy1-iawvqY-uPTd6sbV3rGBsxx1-G5D3DEHW6KwdvmLzuJ763iFxHdCrx7et57NrGLVnr3Ee5ZtTk-q3X8EKMKOIA..&amp;type=2&amp;query=natural language processing" uigs="article_image_6"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/AefvpgiaIPw1IolvRz6yxglEX2Nfzs2UDatTE556JUgEibEF3BfYzcRJasbw9LhZdtU0PPZt76rOnvwXIqUj2LxA/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9BCq5J71JLe73mFQwXCBXmYFjU4ghpkuPEaNfKNFMH_ldsk37JU6194x6bk_fD1tYCdRqGRp4ZG1T6e-chBfqS1iQfLGM4yy1-iawvqY-uPTd6sbV3rGBsxx1-G5D3DEHW6KwdvmLzuJ763iFxHdCrx7et57NrGLVnr3Ee5ZtTk-q3X8EKMKOIA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_6" uigs="article_title_6" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOfx8Jfwfb0qSMYPxNYhbrgS3CozazEQZxAv0VNIHKFwaNalmTkqVilXRXRG3SuJir91JmzcRN4r6ax2AaS46hRV8pxy0f0turddEc0xxIB67PXbnlQaLa-QEceMR0fxVyMpKpo3yAC62WVhzuOmvMIZ120ivibIXEYpQ4WSnA1ak=">ICLR2019最佳论文出炉</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_6">unsupervised parsing, targeted syntactic evaluation, and logical inference.Keywords: Deep Learning, <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>, ...</p>
    <div class="s-p" t="1557123753">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_6" i="oIWsFt76uwDKxyiHVKwWo3xeOGlQ" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzOmfPGPvs25f63z-PZUbG8HxQJWHLEey2lB_Az_B87nOJKBnIhqiDW7MGTbU99d_IxbqfApI7PH6BhddYaTtWZ7hwmGFwNQ87y_bdZbkQO_tbR99V7P4u1eO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM7iathEPUfgnAWr4Hml9INphvANAFNW2LkrRd5RxBqiauzA/0" data-isV="0" uigs="article_account_6">专知</a><span class="s2"><script>document.write(timeConvert('1557123753'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_6"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_6"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_7" d="ab735a258a90e8e1-6bee54fcbd896b2a-741c16f01701774084177b5a936cd5fa">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_7" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6ft3wfAVofsP5Peu-UiA4DFarRdcj931yH0S3dOME6VyVgrFeYQugDskYKcEaA9Zd_fPwmLZ-BpbIAPxv6Ca-Yg5N_EerwQqqnAqa0LXUSeVYaj7ytRnjw7P81Q9AMbS68sh8Uij4jHrfwoM7ynkp0LvKCJTj8nichWMoMp3zNg_Uv32RDw2Y_WNIUknP6gteCJJeGyRkEgcd6evk2DWhqT9yUyikjJPDMm5EDzW2XhE5Dowrhu2EpUTlh7BkrrUJy9pZKNBpq7IJPFHNY8d9xhmU9wp5NOLIiZqwg0yoRFw.&amp;type=2&amp;query=natural language processing" uigs="article_image_7"><i></i><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/koCmZQeYoD3JX70ZQbvSg6cGBVT352cXKicIKcRWEGryJLJ4bP15cRo09icqlDRQ1Jkibob2sicHQNibErMic2vvz74g/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6ft3wfAVofsP5Peu-UiA4DFarRdcj931yH0S3dOME6VyVgrFeYQugDskYKcEaA9Zd_fPwmLZ-BpbIAPxv6Ca-Yg5N_EerwQqqnAqa0LXUSeVYaj7ytRnjw7P81Q9AMbS68sh8Uij4jHrfwoM7ynkp0LvKCJTj8nichWMoMp3zNg_Uv32RDw2Y_WNIUknP6gteCJJeGyRkEgcd6evk2DWhqT9yUyikjJPDMm5EDzW2XhE5Dowrhu2EpUTlh7BkrrUJy9pZKNBpq7IJPFHNY8d9xhmU9wp5NOLIiZqwg0yoRFw.&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_7" uigs="article_title_7" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR-qu0IkVTYmeqBZlKdhwXATCgstBq6judQ7Rlxz0gylCPetsBatxk4gyES6*CMeHfHe6KGHnLR-7m*obdyDT2YDYwWzBgckiZb9fE04cFbeu790Z*YbPkraY5xn-cP-zshsPL5CgfFsNmFz-8G4DSPnGjeKAHpa7ISfQotqwfkE1si2CQNIJQYTGVI3QhXn0x8XHnt*oAxy23FYx13Bv02*5SdMH9Dw7EQXJzkvhsXeAQFix8pDaOT-xeM-UaHtpH5-CenrMVoycfAZoQZ3qkQbwtCHWldUb-jY19HyqhaxkIUFpytq8KSWvv*S*TRkoaMm6ijq7XBxQARM4xwDw9LGcdMPKiwyAepyCZ8MyD664NxlYOlhMeixcHLRXrFE9W4=">老司机们的新问题:如何让导航听懂你的话?</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_7">要让导航具备更好的语音识别功能,就不得不提到一个关键技术&mdash;&mdash;自然<em><!--red_beg-->语言<!--red_end--></em>处理(<em><!--red_beg-->natural<!--red_end--></em> <em><!--red_beg-->language<!--red_end--></em> <em><!--red_beg-->processing<!--red_end--></em>, NLP).听上去不明觉...</p>
    <div class="s-p" t="1478599128">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_7" i="oIWsFt3NcOiNVknqnZevHA71Giyo" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzFOnv2E1njDYhFyB8yP_aCGRH7D7eOeFHAuwnMG-U56AWAFOpAP7ugN98mQTft3hkpCjZUV4N3MQmMm3vzo--sXVHvnWaaYnHDjPB36byG-y64qVv_DjVyeO00efWrWmm&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5qXVicYGRL6g857g9cgttgthcib4nibfPUIUwvmm1O2rwiaA/0" data-isV="1" uigs="article_account_7">华为</a><span class="s2"><script>document.write(timeConvert('1478599128'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_7"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_7"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_8" d="ab735a258a90e8e1-6bee54fcbd896b2a-60d08bcd80ab42ad063206adcda2f852">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_8" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nQDQF7x2OEA00mgehHClBAfqy0aRVa29aRqNmCF8nG9hj4qG8h8FlcvrGGMr4b6MOH-QkLwT_4W1SovJX_o20_3cY5xkJyPbXT_T6eE0LZ6pfAmnEcWfAbVhlgeRt7bSzA..&amp;type=2&amp;query=natural language processing" uigs="article_image_8"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/nW2ZPfuYqSLC3tcmMfNZslbOrxdsCcDyMmpBjXx4N17hW9xS74QLBuOOkx8L8aXgIibgt6Lq9aibwATkSFw4Ujnw/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9riZqsuUMLYiT4vb2sU8D_qw2OHzjlbnwcvxHH-30Cp8ZmK-cjyf5nQDQF7x2OEA00mgehHClBAfqy0aRVa29aRqNmCF8nG9hj4qG8h8FlcvrGGMr4b6MOH-QkLwT_4W1SovJX_o20_3cY5xkJyPbXT_T6eE0LZ6pfAmnEcWfAbVhlgeRt7bSzA..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_8" uigs="article_title_8" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOo*Ts1qexnqKcdyu1c5XfaffGF4UDvac7JhL7P1HbVIifDsxGjKf1GWwi*diS2Fq3bVOC1dx0Vz75vBmcN1aaa5yQTFSUl4tVIjgJj7b6R-K*bSsOEfBeQuoLLR3PsutHa8j6XC5qE4d7L6etI-TIHq*y-PXg8Ap*3ewQ7JlXPE0=">一位硕士应届生的AI修炼之道及NLP新年＂大礼包＂</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_8">包括视频、PPT讲义.Oxford Course on Deep Learning for <em><!--red_beg-->Natural<!--red_end--></em> <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em>:https://machinelearningmastery.com/oxford-...</p>
    <div class="s-p" t="1549186992">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_8" i="oIWsFtz7PCYo9ze51qMgGgRusEj0" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdz_o3KSj2BQzATpAA8QcOh4HtoExjPCeshBN6QwrGnZyZzI7UhV62l3TAtGzG4ot1vwD7lGdcUClBcDsMxZaxfVYK3IpghcFH0Bgq1Uoy787bv9uEPU0m8zqUiiWOv1GPM&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM67GK57pic5p6OCgaEI1EzCbxGR4M8mZ9GziaXhcNvj743A/0" data-isV="0" uigs="article_account_8">AINLP</a><span class="s2"><script>document.write(timeConvert('1549186992'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_8"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_8"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    		<!-- a -->
    		<li id="sogou_vr_11002601_box_9" d="ab735a258a90e8e1-6bee54fcbd896b2a-2c7faf07d6972ce34408e87eebe4b847">
    <div class="img-box">
    <a data-z="art" target="_blank" id="sogou_vr_11002601_img_9" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YbCBqWa2x5mxzNZT5ta0ijegdSVa_u33OuTNP9IjG0SZ_bUPs6nnoXVh4eEnHQCA5wDdo0fuvGli_7IP9CbWcr9mN35Vd8vGU-AOwW-rwcfegT6DbBa2vPMIIY5Pifyqz2S771JEfXl74R_R4ukZNasBvqz8bq26PCLExB_reCV5Nu7CnoSqqg..&amp;type=2&amp;query=natural language processing" uigs="article_image_9"><img src="//img01.sogoucdn.com/net/a/04/link?appid=100520033&amp;url=http://mmbiz.qpic.cn/mmbiz_jpg/EkgpOcjaJwgGwzIia58tqnntO1xErQCt8nicOYHW4pALvhbqwyj2TibnWkibPIWZl1JrTqFAleg5hMfFm9botV0okg/0?wx_fmt=jpeg" onload="resizeImage(this,140,105)" onerror="errorImage(this)"></a>
    </div>
    <div class="txt-box">
    <h3>
    <a target="_blank" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6cwJThYulHEtVjXrGTiVgSwaaJJjZkknW_VwRg2bqHjGyZY1qgS8UV1qXa8Fplpd9YbCBqWa2x5mxzNZT5ta0ijegdSVa_u33OuTNP9IjG0SZ_bUPs6nnoXVh4eEnHQCA5wDdo0fuvGli_7IP9CbWcr9mN35Vd8vGU-AOwW-rwcfegT6DbBa2vPMIIY5Pifyqz2S771JEfXl74R_R4ukZNasBvqz8bq26PCLExB_reCV5Nu7CnoSqqg..&amp;type=2&amp;query=natural language processing" id="sogou_vr_11002601_title_9" uigs="article_title_9" data-share="http://weixin.sogou.com/api/share?timestamp=1562763693&amp;signature=qIbwY*nI6KU9tBso4VCd8lYSesxOYgLcHX5tlbqlMR8N6flDHs4LLcFgRw7FjTAOhmMWZF*YQQ-TXVUUIrxEM3iuAxA1i0CKL3eKzbbNxBvc2bHizN*5l1MZttbcGLUGLpYdsNWz1GPWG0YLrgRov11h6DeQCCJlV*1DLrX7pLBHazKfyuDCIqMS*eP1uyqdo*r4ufjj*HrIt2ESADulaWlTPI-4TaG4pcB4M7ukZGA=">如何拥抱 embedding ?从词向量到句向量的技术详解</a>
    </h3>
    <p class="txt-info" id="sogou_vr_11002601_summary_9">其他为扩展的:Reference:Books and CoursesJurafsky, Dan. Speech and <em><!--red_beg-->Language<!--red_end--></em> <em><!--red_beg-->Processing<!--red_end--></em> (3rd ed. 2019)CS224n: <em><!--red_beg-->Natural<!--red_end--></em> ...</p>
    <div class="s-p" t="1560830103">
    <a class="account" target="_blank" id="sogou_vr_11002601_account_9" i="oIWsFtwlD0icszBtRc2mEegYz_fU" href="/link?url=dn9a_-gY295K0Rci_xozVXfdMkSQTLW6EzDJysI4ql5MPrOUp16838dGRMI7NnPqwmCjrvk_i_8RHeAXPrs9mQwvDqyjOWdzmt-nF4NtLQt8eKXXzIad1o8WF2ORouWhwztHsL4bQdGFNdTWezUJndLRNcZFArIJqercsAI_hpUmT7rS8udeklVHNWR0LrYwrcDSWovf-w8rGUoeAkK7YWRTpLLTNgHY&amp;type=2&amp;query=natural language processing" data-headimage="http://wx.qlogo.cn/mmhead/Q3auHgzwzM5DUO6JVFyhCXiaxDIdwCQGfuhjuibxFlE2xMsoNx9zQOKA/0" data-isV="1" uigs="article_account_9">阿里机器智能</a><span class="s2"><script>document.write(timeConvert('1560830103'))</script></span>
    <div class="moe-box">
    <span style="display:none;" class="sc"><a data-except="1" class="sc-a" href="javascript:void(0)" uigs="share_9"></a></span><span style="display:none;" class="fx"><a data-except="1" class="fx-a" href="javascript:void(0)" uigs="like_9"></a></span>
    </div>
    </div>
    </div>
    </li>
    
    		<!-- z -->
    	
    </ul>
        
            <p class="look-more" style="display: none;">当前只显示前100条内容，<a href="javascript:void(0)" name="top_login" uigs="home_login_100_art_search">登录</a>&nbsp;可查看更多。</p>
        
    <div class="p-fy" id="pagebar_container">
    	
    			<a id="sogou_prev" href="?query=natural+language+processing&type=2&page=9&ie=utf8" class="pev" uigs="page_before">上一页</a>
    			
    				<a id="sogou_page_1" href="?query=natural+language+processing&type=2&page=1&ie=utf8" uigs="page_1">1</a>
    				
    					<b style="float:left;font-weight:normal;margin-right:10px">...</b>
    				<a id="sogou_page_6" href="?query=natural+language+processing&type=2&page=6&ie=utf8" uigs="page_6">6</a><a id="sogou_page_7" href="?query=natural+language+processing&type=2&page=7&ie=utf8" uigs="page_7">7</a><a id="sogou_page_8" href="?query=natural+language+processing&type=2&page=8&ie=utf8" uigs="page_8">8</a><a id="sogou_page_9" href="?query=natural+language+processing&type=2&page=9&ie=utf8" uigs="page_9">9</a><span>10</span>
    		<div class="mun">找到约450条结果<!--resultbarnum:450--></div>
    </div>
        
    </div>
    
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "null_90-null_91-null_92-null_93-null_94-null_95-null_96-null_97-null_98-null_99-";
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
    <!--1562763693798-->
    <!--zly--><!--weixin-->
    
    
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
            var uuid = "edc758df-2380-4ee2-9513-6a3ab1f89c0c";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693845;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693845",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "edc758df-2380-4ee2-9513-6a3ab1f89c0c",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "",
                "exp_id_list"   : "",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A534AD1EE42F2E1C",
                "rn"            : 0,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "11"
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
        
    </div>
    
    
    <script>
        $(".news-box").remove();
    </script>
    
    <div class="b404-box" id="noresult_part1_container" style="padding-right:40px; width:530px">
    	<img src="/new/pc/images/bg_404_2.png" width="217" height="217">
    	<div class="text-info" style="left:280px">
    		<p class="p1">呀！</p>
    		<p class="p3">
    		<p class="p3">
    						当前只显示100条结果，请您：<br/>
    						<a href="javascript:void(0)" name="top_login" data-type="noresult" uigs="home_login_100_noresult">登录</a>&nbsp;后查看更多结果，<br/>
    						或者&nbsp;<a href="https://weixin.sogou.com" uigs="other_noresult_back_index">返回微信搜索首页</a>
    					</p>
    		</p>
    	</div>
    </div>
    <div><iframe scrolling="no" frameborder="0" src="https://yibo.iyiyun.com/Home/Distribute/ad404/key/17812" width="545" height="340" style="display:block;"></iframe></div>
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "";
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
    <!--1562763693844-->
    <!--tmd-->
    <!--lyc-->
    
    
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
            var uuid = "90b44e4d-8b63-40f2-97bc-30b68bf0aa5e";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693891;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693891",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "90b44e4d-8b63-40f2-97bc-30b68bf0aa5e",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "",
                "exp_id_list"   : "",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A5341B7AE42F2E2D",
                "rn"            : 0,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "12"
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
        
    </div>
    
    
    <script>
        $(".news-box").remove();
    </script>
    
    <div class="b404-box" id="noresult_part1_container" style="padding-right:40px; width:530px">
    	<img src="/new/pc/images/bg_404_2.png" width="217" height="217">
    	<div class="text-info" style="left:280px">
    		<p class="p1">呀！</p>
    		<p class="p3">
    		<p class="p3">
    						当前只显示100条结果，请您：<br/>
    						<a href="javascript:void(0)" name="top_login" data-type="noresult" uigs="home_login_100_noresult">登录</a>&nbsp;后查看更多结果，<br/>
    						或者&nbsp;<a href="https://weixin.sogou.com" uigs="other_noresult_back_index">返回微信搜索首页</a>
    					</p>
    		</p>
    	</div>
    </div>
    <div><iframe scrolling="no" frameborder="0" src="https://yibo.iyiyun.com/Home/Distribute/ad404/key/17812" width="545" height="340" style="display:block;"></iframe></div>
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "";
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
    <!--1562763693891-->
    <!--tmd-->
    <!--lyc-->
    
    
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
            var uuid = "42bd029e-8486-4e54-8130-64fc5a23d812";
            var keywords_string = "natural language processing";
            var sab = "2";
            var keywords = oldQuery.split(' ');
            var now = 1562763693924;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693924",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "42bd029e-8486-4e54-8130-64fc5a23d812",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "",
                "exp_id_list"   : "",
                "wuid"          : "",
                "snuid"         : "1609E397E4E169B0A53B7A2AE42F2E18",
                "rn"            : 0,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "13"
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
        
    </div>
    
    
    <script>
        $(".news-box").remove();
    </script>
    
    <div class="b404-box" id="noresult_part1_container" style="padding-right:40px; width:530px">
    	<img src="/new/pc/images/bg_404_2.png" width="217" height="217">
    	<div class="text-info" style="left:280px">
    		<p class="p1">呀！</p>
    		<p class="p3">
    		<p class="p3">
    						当前只显示100条结果，请您：<br/>
    						<a href="javascript:void(0)" name="top_login" data-type="noresult" uigs="home_login_100_noresult">登录</a>&nbsp;后查看更多结果，<br/>
    						或者&nbsp;<a href="https://weixin.sogou.com" uigs="other_noresult_back_index">返回微信搜索首页</a>
    					</p>
    		</p>
    	</div>
    </div>
    <div><iframe scrolling="no" frameborder="0" src="https://yibo.iyiyun.com/Home/Distribute/ad404/key/17812" width="545" height="340" style="display:block;"></iframe></div>
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "";
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
    <!--1562763693924-->
    <!--tmd-->
    <!--lyc-->
    
    
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
            var uuid = "285f5eec-677c-4cc5-bc7b-1a948d947643";
            var keywords_string = "natural language processing";
            var sab = "1";
            var keywords = oldQuery.split(' ');
            var now = 1562763693970;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763693970",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "285f5eec-677c-4cc5-bc7b-1a948d947643",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "",
                "exp_id_list"   : "",
                "wuid"          : "",
                "snuid"         : "C3DC31413630BB6673EC673C361BEA70",
                "rn"            : 0,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "14"
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
        
    </div>
    
    
    <script>
        $(".news-box").remove();
    </script>
    
    <div class="b404-box" id="noresult_part1_container" style="padding-right:40px; width:530px">
    	<img src="/new/pc/images/bg_404_2.png" width="217" height="217">
    	<div class="text-info" style="left:280px">
    		<p class="p1">呀！</p>
    		<p class="p3">
    		<p class="p3">
    						当前只显示100条结果，请您：<br/>
    						<a href="javascript:void(0)" name="top_login" data-type="noresult" uigs="home_login_100_noresult">登录</a>&nbsp;后查看更多结果，<br/>
    						或者&nbsp;<a href="https://weixin.sogou.com" uigs="other_noresult_back_index">返回微信搜索首页</a>
    					</p>
    		</p>
    	</div>
    </div>
    <div><iframe scrolling="no" frameborder="0" src="https://yibo.iyiyun.com/Home/Distribute/ad404/key/17812" width="545" height="340" style="display:block;"></iframe></div>
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "";
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
    <!--1562763693970-->
    <!--tmd-->
    <!--lyc-->
    
    
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
            var uuid = "12a0ffb6-85a6-435c-8a75-d02d325f29e7";
            var keywords_string = "natural language processing";
            var sab = "0";
            var keywords = oldQuery.split(' ');
            var now = 1562763694098;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763694098",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "12a0ffb6-85a6-435c-8a75-d02d325f29e7",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "",
                "exp_id_list"   : "",
                "wuid"          : "",
                "snuid"         : "C3DC31413630BB6673EE1DB6361BEADE",
                "rn"            : 0,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "15"
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
        
    </div>
    
    
    <script>
        $(".news-box").remove();
    </script>
    
    <div class="b404-box" id="noresult_part1_container" style="padding-right:40px; width:530px">
    	<img src="/new/pc/images/bg_404_2.png" width="217" height="217">
    	<div class="text-info" style="left:280px">
    		<p class="p1">呀！</p>
    		<p class="p3">
    		<p class="p3">
    						当前只显示100条结果，请您：<br/>
    						<a href="javascript:void(0)" name="top_login" data-type="noresult" uigs="home_login_100_noresult">登录</a>&nbsp;后查看更多结果，<br/>
    						或者&nbsp;<a href="https://weixin.sogou.com" uigs="other_noresult_back_index">返回微信搜索首页</a>
    					</p>
    		</p>
    	</div>
    </div>
    <div><iframe scrolling="no" frameborder="0" src="https://yibo.iyiyun.com/Home/Distribute/ad404/key/17812" width="545" height="340" style="display:block;"></iframe></div>
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "";
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
    <!--1562763694098-->
    <!--tmd-->
    <!--lyc-->
    
    
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
            var uuid = "38c9a47c-f422-43e2-8fe5-faf83864f0b2";
            var keywords_string = "natural language processing";
            var sab = "8";
            var keywords = oldQuery.split(' ');
            var now = 1562763694147;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763694147",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "38c9a47c-f422-43e2-8fe5-faf83864f0b2",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "",
                "exp_id_list"   : "",
                "wuid"          : "",
                "snuid"         : "C3DC31413630BB6673EED3B1361BEACD",
                "rn"            : 0,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "16"
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
        
    </div>
    
    
    <script>
        $(".news-box").remove();
    </script>
    
    <div class="b404-box" id="noresult_part1_container" style="padding-right:40px; width:530px">
    	<img src="/new/pc/images/bg_404_2.png" width="217" height="217">
    	<div class="text-info" style="left:280px">
    		<p class="p1">呀！</p>
    		<p class="p3">
    		<p class="p3">
    						当前只显示100条结果，请您：<br/>
    						<a href="javascript:void(0)" name="top_login" data-type="noresult" uigs="home_login_100_noresult">登录</a>&nbsp;后查看更多结果，<br/>
    						或者&nbsp;<a href="https://weixin.sogou.com" uigs="other_noresult_back_index">返回微信搜索首页</a>
    					</p>
    		</p>
    	</div>
    </div>
    <div><iframe scrolling="no" frameborder="0" src="https://yibo.iyiyun.com/Home/Distribute/ad404/key/17812" width="545" height="340" style="display:block;"></iframe></div>
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "";
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
    <!--1562763694147-->
    <!--tmd-->
    <!--lyc-->
    
    
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
            var uuid = "3952a1ac-55c0-40aa-96c0-4346fd15c259";
            var keywords_string = "natural language processing";
            var sab = "0";
            var keywords = oldQuery.split(' ');
            var now = 1562763694224;
            var idc = "sjs";
            var clientIp = "116.7.234.245";
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
                "uigs_t": "1562763694224",
                "uigs_productid": "vs_web",
                "terminal"      : "web",
                "vstype"        : "weixin",
                "pagetype"      : "result",
                "channel"       : "result_article",
                "s_from"        : "",
                "sourceid"      : "",
                "type"          : "weixin_search_pc",
                "uigs_cookie"   : "SUID,sct",
                "uuid"          : "3952a1ac-55c0-40aa-96c0-4346fd15c259",
                "query"         : "natural language processing",
                "weixintype"    : "2",
                "exp_status"    : "",
                "exp_id_list"   : "",
                "wuid"          : "",
                "snuid"         : "C3DC31413630BB6673E9BCDB361BEA38",
                "rn"            : 0,
                "login"         : passportUserId ? "1" : "0",
                "uphint"        : 0,
                "bottomhint"    : 1,
                "page"          : "17"
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
        
    </div>
    
    
    <script>
        $(".news-box").remove();
    </script>
    
    <div class="b404-box" id="noresult_part1_container" style="padding-right:40px; width:530px">
    	<img src="/new/pc/images/bg_404_2.png" width="217" height="217">
    	<div class="text-info" style="left:280px">
    		<p class="p1">呀！</p>
    		<p class="p3">
    		<p class="p3">
    						当前只显示100条结果，请您：<br/>
    						<a href="javascript:void(0)" name="top_login" data-type="noresult" uigs="home_login_100_noresult">登录</a>&nbsp;后查看更多结果，<br/>
    						或者&nbsp;<a href="https://weixin.sogou.com" uigs="other_noresult_back_index">返回微信搜索首页</a>
    					</p>
    		</p>
    	</div>
    </div>
    <div><iframe scrolling="no" frameborder="0" src="https://yibo.iyiyun.com/Home/Distribute/ad404/key/17812" width="545" height="340" style="display:block;"></iframe></div>
    
            </div>
            
                <div class="snb-right" id="right">
                    
    
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
            uigs_para.exp_id = "";
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
    <!--1562763694224-->
    <!--tmd-->
    <!--lyc-->
    
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    出现了错误：302
    None
    
