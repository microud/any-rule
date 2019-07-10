# 正则大全 ![](https://img.shields.io/badge/已收录-47条-4caf50.svg) ![](https://img.shields.io/badge/license-MIT-F44336.svg)
:whale:图形界面: https://any86.github.io/any-rule/


## html注释
```javascript
/<!--(.*?)-->/
```

## md5格式(32位)
```javascript
/^[a-f0-9]{32}$/
```

## 版本号格式必须为X.Y.Z
```javascript
/^\d+(\.\d+){2}$/
```

## 视频链接地址（视频格式可按需增删）
```javascript
/^https?:\/\/.*?(swf|avi|flv|mpg|rm|mov|wav|asf|3gp|mkv|rmvb|mp4)$/i
```

## 图片链接地址（图片格式可按需增删）
```javascript
/^https?:\/\/.*?(gif|png|jpg|jpeg|webp|svg|psd|bmp|tif)$/i
```

## 24小时制时间（HH:mm:ss）
```javascript
/^((?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d$)/
```

## 12小时制时间（hh:mm:ss）
```javascript
/^(1[0-2]|0?[1-9]):[0-5]\d:[0-5]\d$/
```

## base64格式
```javascript
/^\s*data:([a-z]+\/[a-z0-9-+.]+(;[a-z-]+=[a-z0-9-]+)?)?(;base64)?,([a-z0-9!$&',()*+;=\-._~:@\/?%\s]*?)\s*$/i
```

## 数字/货币金额（支持负数、千分位分隔符）
```javascript
/(^[-]?[1-9]\d{0,2}($|(,\d{3})*($|(\.\d{1,2}$))))|((^[0](\.\d{1,2})?)|(^[-][0]\.\d{1,2}))$/
```

## 数字/货币金额 (只支持正数、不支持校验千分位分隔符)
```javascript
/(^[1-9]([0-9]+)?(\.[0-9]{1,2})?$)|(^(0){1}$)|(^[0-9]\.[0-9]([0-9])?$)/
```

## 银行卡号（16或19位）
```javascript
/^([1-9]{1})(\d{15}|\d{18})$/
```

## 中文姓名
```javascript
/^([\u4e00-\u9fa5·]{2,16})$/
```

## 英文姓名
```javascript
/(^[a-zA-Z]{1}[a-zA-Z\s]{0,20}[a-zA-Z]{1}$)/
```

## 新能源车牌号
```javascript
/[京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领 A-Z]{1}[A-HJ-NP-Z]{1}(([0-9]{5}[DF])|([DF][A-HJ-NP-Z0-9][0-9]{4}))$/
```

## 非新能源车牌号
```javascript
/^[京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领 A-Z]{1}[A-HJ-NP-Z]{1}[A-Z0-9]{4}[A-Z0-9挂学警港澳]{1}$/
```

## 车牌号(新能源+非新能源)
```javascript
/^([京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领 A-Z]{1}[A-HJ-NP-Z]{1}(([0-9]{5}[DF])|([DF]([A-HJ-NP-Z0-9])[0-9]{4})))|([京津沪渝冀豫云辽黑湘皖鲁新苏浙赣鄂桂甘晋蒙陕吉闽贵粤青藏川宁琼使领 A-Z]{1}[A-Z]{1}[A-HJ-NP-Z0-9]{4}[A-HJ-NP-Z0-9 挂学警港澳]{1})$/
```

## URL链接(网址)
```javascript
/^((https?|ftp|file):\/\/)?([\da-z.-]+)\.([a-z.]{2,6})(\/\w\.-]*)*\/?/
```

## 手机号(严谨), 根据工信部2019年最新公布的手机号段
```javascript
/^1((3[\d])|(4[5,6,7,9])|(5[0-3,5-9])|(6[5-7])|(7[0-8])|(8[\d])|(9[1,8,9]))\d{8}$/
```

## 手机号(宽松), 只要是13,14,15,16,17,18,19开头即可
```javascript
/^1[3-9]\d{9}$/
```

## 手机号(最宽松), 只要是1开头即可, 如果你的手机号是用来接收短信, 优先建议选择这一条
```javascript
/^1\d{10}$/
```

## 日期, 如: 2000-01-01或2000-1-1
```javascript
/^\d{4}(-)([0-1][0-2]|\d)\1([0-2]\d|\d|30|31)$/
```

## email地址
```javascript
/^[a-zA-Z0-9.!#$%&'*+\/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/
```

## 国内座机电话,如: 0341-86091234
```javascript
/\d{3}-\d{8}|\d{4}-\d{7}/
```

## 一代身份证号(15位数字)
```javascript
/^\d{8}(0\d|10|11|12)([0-2]\d|30|31)\d{3}$/
```

## 二代身份证号(18位数字),最后一位是校验位,可能为数字或字符X
```javascript
/^\d{6}(18|19|20)\d{2}(0\d|10|11|12)([0-2]\d|30|31)\d{3}(\d|X|x)$/
```

## 身份证号, 支持1/2代(15位/18位数字)
```javascript
/(^\d{8}(0\d|10|11|12)([0-2]\d|30|31)\d{3}$)|(^\d{6}(18|19|20)\d{2}(0\d|10|11|12)([0-2]\d|30|31)\d{3}(\d|X|x)$)/
```

## 护照（包含香港、澳门）
```javascript
/(^[EeKkGgDdSsPpHh]\d{8}$)|(^(([Ee][a-fA-F])|([DdSsPp][Ee])|([Kk][Jj])|([Mm][Aa])|(1[45]))\d{7}$)/
```

## 帐号是否合法(字母开头，允许5-16字节，允许字母数字下划线组合
```javascript
/^[a-zA-Z][a-zA-Z0-9_]{4,15}$/
```

## 纯中文/汉字
```javascript
/^[\u4E00-\u9FA5]+$/
```

## 是否小数
```javascript
/^\d+\.\d+$/
```

## 电话(座机)
```javascript
/^0\d{2,3}-\d{7,8}$/
```

## 纯数字
```javascript
/^\d{1,}$/
```

## 是否html标签
```javascript
/<(.*)>.*<\/\1>|<(.*) \/>/
```

## 是否qq号格式正确
```javascript
/^[1-9][0-9]{4,10}$/
```

## 是否由数字和字母组成
```javascript
/^[A-Za-z0-9]+$/
```

## 纯英文字母
```javascript
/^[a-zA-Z]+$/
```

## 纯小写英文字母组成
```javascript
/^[a-z]+$/
```

## 纯大写英文字母
```javascript
/^[A-Z]+$/
```

## 密码强度正则，最少6位，包括至少1个大写字母，1个小写字母，1个数字，1个特殊字符
```javascript
/^.*(?=.{6,})(?=.*\d)(?=.*[A-Z])(?=.*[a-z])(?=.*[!@#$%^&*? ]).*$/
```

## 用户名正则，4到16位（字母，数字，下划线，减号）
```javascript
/^[a-zA-Z0-9_-]{4,16}$/
```

## ip-v4
```javascript
/^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$/
```

## ip-v6
```javascript
/^((([0-9A-Fa-f]{1,4}:){7}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){6}:[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){5}:([0-9A-Fa-f]{1,4}:)?[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){4}:([0-9A-Fa-f]{1,4}:){0,2}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){3}:([0-9A-Fa-f]{1,4}:){0,3}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){2}:([0-9A-Fa-f]{1,4}:){0,4}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){6}((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|(([0-9A-Fa-f]{1,4}:){0,5}:((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|(::([0-9A-Fa-f]{1,4}:){0,5}((\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b)\.){3}(\b((25[0-5])|(1\d{2})|(2[0-4]\d)|(\d{1,2}))\b))|([0-9A-Fa-f]{1,4}::([0-9A-Fa-f]{1,4}:){0,5}[0-9A-Fa-f]{1,4})|(::([0-9A-Fa-f]{1,4}:){0,6}[0-9A-Fa-f]{1,4})|(([0-9A-Fa-f]{1,4}:){1,7}:))$/i
```

## 16进制颜色
```javascript
/^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$/
```

## 微信号，6至20位，以字母开头，字母，数字，减号，下划线
```javascript
/^[a-zA-Z]([-_a-zA-Z0-9]{5,19})+$/
```

## 中国邮政编码
```javascript
/^(0[1-7]|1[0-356]|2[0-7]|3[0-6]|4[0-7]|5[1-7]|6[1-7]|7[0-5]|8[013-6])\d{4}$/
```

## 只包含中文和数字
```javascript
/^(([\u4E00-\u9FA5])|(\d))+$/
```

## 非字母
```javascript
/[^A-Za-z]$/
```
