# 全选全不选以及监听取消全选或自动全选

效果如下：
![](images/img.gif)
fdsfd
demo code:
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>全选全不选以及监听取消全选或自动全选</title>
    <style>
        .bg{
            background-image: url(images/list_bg.gif);
            background-repeat: no-repeat;
            width: 730px;
        }
        td{text-align:center;
            font-size:13px;
            line-height:25px;
        }
        body{margin:0}
    </style>
</head>
<body>
<table border="0" cellspacing="0" cellpadding="0" class="bg">
    <form action="" method="post">
        <tr>
            <td style="height:40px;">&nbsp;</td>
            <td>&nbsp;</td>
            <td>&nbsp;</td>
            <td>&nbsp;</td>
        </tr>
        <tr style="font-weight:bold;">
            <td>
                <input id="all" type="checkbox" value="全选" />
                全选
            </td>
            <td>商品图片</td>
            <td>商品名称/出售者/联系方式</td>
            <td>价格</td>
        </tr>
        <tr>
            <td colspan="4">
                <hr style="border:1px  #CCCCCC dashed" />
            </td>
        </tr>
        <tr>
            <td>
                <input name="product" type="checkbox" value="1" />
            </td>
            <td>
                <img src="images/list0.jpg" alt="alt" />
            </td>
            <td>
                杜比环绕，家庭影院必备，超真实享受<br />
                出售者：ling112233<br />
                <img src="images/online_pic.gif" alt="alt" /> &nbsp;&nbsp;
                <img src="images/list_tool_fav1.gif" alt="alt" />
                收藏
            </td>
            <td>一口价<br />
                2833.0
            </td>
        </tr>
        <tr>
            <td colspan="4"><hr style="border:1px  #CCCCCC dashed" /></td>
        </tr>
        <tr>
            <td>
                <input name="product" type="checkbox" value="2" />
            </td>
            <td>
                <img src="images/list1.jpg" alt="alt" />
            </td>
            <td>
                NVDIA 9999GT 512MB 256bit极品显卡，不容错过<br />
                出售者：aipiaopiao110 <br />
                <img src="images/online_pic.gif" alt="alt" /> &nbsp;&nbsp;
                <img src="images/list_tool_fav1.gif" alt="alt" /> 收藏
            </td>
            <td>
                一口价<br />
                6464.0
            </td>
        </tr>
        <tr>
            <td colspan="4"><hr style="border:1px  #CCCCCC dashed" /></td>
        </tr>
        <tr>
            <td><input name="product" type="checkbox" value="3" /></td>
            <td><img src="images/list2.jpg" alt="alt" /></td>
            <td>精品热卖：高清晰，30寸等离子电视<br />
                出售者：阳光的挣扎 <br />
                <img src="images/online_pic.gif" alt="alt" /> &nbsp;&nbsp;
                <img src="images/list_tool_fav1.gif" alt="alt" /> 收藏
            </td>
            <td>一口价<br />
                18888.0
            </td>
        </tr>
        <tr>
            <td colspan="4"><hr style="border:1px  #CCCCCC dashed" /></td>
        </tr>
        <tr>
            <td><input name="product" type="checkbox" value="4" /></td>
            <td><img src="images/list3.jpg" alt="alt" /></td>
            <td>Sony索尼家用最新款笔记本 <br />
                出售者：疯狂的镜无<br />
                <img src="images/online_pic.gif" alt="alt" /> &nbsp;&nbsp;
                <img src="images/list_tool_fav1.gif" alt="alt" /> 收藏
            </td>
            <td>一口价<br />
                5889.0
            </td>
        </tr>
        <tr>
            <td colspan="4"><hr style="border:1px  #CCCCCC dashed" /></td>
        </tr>
    </form>
</table>
</body>
</html>
<script>
/*
 * 点全选，全部选择或者全部取消
 * 点其余任意一个自动判断全选是否需要选上[重点]
 * js必须写在下面，否则需要onload函数
 * */
var all = document.getElementById("all"),
        product = document.getElementsByName("product"),
        l = product.length;
all.onclick = function(){
    for(var i=l;i--;){
        product[i].checked = all.checked;
    }
};
for(var i=l;i--;){
    product[i].onclick = function(){
        var k = 0;
        for(var i=l;i--;)product[i].checked && k++;
        all.checked = l==k;
    };
}
</script>
```


