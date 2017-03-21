# `:first-child` & `:last-child` bugs?


https://gist.github.com/xgqfrms-GitHub/7bb92ccb71a6c558708f24172bf1898d



## need parent div container





## `:nth-of-type` is OK!


```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>account-info</title>
    <style>
        body, div{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            overflow: hidden;
        }
        .account-info-box{
            width: calc(100% - 46px);
            /*max-width: 1484px;*/
            /*min-width: 1000px;*/
            background: #fff;
            /*min-height: 100px;*/
            /*height: 150px;
            line-height: 150px;*/
            /*text-align: center;*/
            border: 1px solid #ccc;
            box-sizing: border-box;
            /*overflow: hidden;*/
            margin: 5px 23px;
            position: relative;
        }
        .account-info-logo{
            background: url(./orders/person.png) no-repeat;
            width: 300px;
            height: 150px;
            background-position: 30px 30px;
        }
        .account-info-logo-span1, .account-info-logo-span2{
            /*float: left;*/
            display: inline-block;
            margin-left: 150px;
            margin-top: 10px;
            font-size: 16px;
            color: #888;
        }
        .account-info-logo-span1{
            margin-top: 50px;
        }
        .account-info-line{
            width: 1;
            height: 80px;
            border: 1px solid #ccc;
            position: absolute;
            top: 40px;
            left: 350px;
        }
        .account-info-text{
            /*clear: both;*/
            position: absolute;
            left: 400px;
            /*margin-top: 10px;*/
            top: 40px;
            height: 100px;
        }
        .account-info-text > span{
            display: inline-block;
            margin: 3px;
            font-size: 16px;
        }
        .account-info-text > span::after{
            font-size: 12px;
            display: block;
            color: #0bf;
        }
        .account-info-text > span:nth-of-type(1)::after{
            content: "最近十天佣金金额：￥500.00";
        }
        .account-info-text > span:nth-of-type(2)::after{
            content: "请及时结算待缴佣金，以免影响您的商品售卖";
        }
        /*.account-info-text > span:nth-last-child::after{
            content: "请及时结算待缴佣金，以免影响您的商品售卖";
        }*/
        .account-info-text-btn{
            margin-left: 400px;
            margin-top: -60px;
        }
        .account-info-text-btn button{
            height: 30px;
            color: #fff;
            border: 1px solid #fff;
            margin-left: 10px;
        }
        .account-info-text-btn button:first-child{
            width: 50px;
            background: #CCE4F7;
        }
        .account-info-text-btn button{
            width: 100px;
            background: #0bf;
        }
    </style>
</head>
<body>
    <div>
        <div class="account-info-box">
            <div class="account-info-logo">
                <span class="account-info-logo-span1">15864655455</span>
                <span class="account-info-logo-span2">综合：4.5</span>
            </div>
            <div class="account-info-line"></div>
            <div class="account-info-text">
                <span>预付佣金：￥10000</span><br>
                <span>待缴佣金：￥20.00</span>
                <div class="account-info-text-btn">
                    <button>充值</button>
                    <button>配送员设置</button>
                </div>
            </div>
        </div>
    </div>
</body>
</html>

```






