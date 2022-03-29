# SQLINJECTIONTEST
資安項目檢驗
其實就是捉JS 去對後端資料做出修改
# 搶場用 
## 第一正常版本
``` =js
document.getElementsByName('place')[0]['0']['10'].selected =1
//
document.getElementsByName('place')[0]['1']['日期替換ˋ'].selected =1//今天(+1~6)
//
document.getElementsByName('place')[0]['2'].click()
```

## 第二
``` =js
document.querySelector('tr:nth-child(3) > td:nth-child(6) td:nth-child(2)').click() 
//First: row 2 to n  Second: column 1 to n  Third:  child column 1(half) and 2 (full)
```
# 注入版本 
:::success
這邊的id 是會異常帶需要被找尋
``` =js 
document.getElementsByName('place')[0]['0']['10'].selected =1
document.getElementsByName('place')[0]['1']['1'].value =XXXX/MM/DD 星期X
```
:::
## 待解決區
:::success
都可以找到相對應的日期 
```
document.getElementsByName('style4')['0'].innerHTML= YYYY/MM/DD
document.getElementsByName('style4')['2'].innerHTML= 廠區
```
:::
:::
會發生ID 異常的情況 但是我還在思考該如何解決
因為第二個資料庫(查詢資料庫)並不會顯示出來
等於整個注入法沒成功沒證據
:::
