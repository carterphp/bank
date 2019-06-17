# bank
这是一个简单的查询银行及银行卡信息的类，主要分为三个功能

#### composer 安装

```
composer require carterphp/bank
```



### PS:收集银行卡信息是一个缓慢更新的过程，只有起点，没有终点，如果各位发现有遗漏的，欢迎补充添加；



#### 功能一:检测银行卡格式是否正确

调用:

```
$bank = new Bankcard();
$res = $bank->checkFormat('622700287287000000');  //此处传入银行卡号
return $res;
```

返回：

```
0：银行卡格式错误
1：银行卡格式正确
```



#### 功能二:根据银行卡号获取银行卡基础信息

调用：

```
$bank = new Bankcard();
$res = $bank->info('622700287287000000');   //此处传入银行卡号
return $res;
```

返回：

```
{
    "code": 0,
    "msg": "操作成功",
    "data": [
        {
            "card_style": "龙卡储蓄卡(银联卡)",   //卡类型
            "bank_code": "105100000017",        //银行联行号
            "bank_name": "建设银行",             //名称
            "card_type": "储蓄卡",               //卡种
            "letter_code": "CCB"                //银行字母编码
        }
    ]
}
```

#### 功能三:根据银行简码获取银行信息

调用：

```
$bank = new Bankcard();
$res = $bank->getBankInfo('icbc');   //此处传入银行字母简码(不区分大小写)
return $res;
```

返回：

```
{
    "code": 0,
    "msg": "操作成功",
    "data": [
        {
            "bank_code": "01020000",   //联行号
            "bank_name": "工商银行"     //名称
        }
    ]
}
```

