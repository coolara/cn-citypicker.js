# cn-citypicker.js
js省市联动菜单(无依赖/无样式)

@author Meng G. <gaomeng1900#gmail.com>
@version 1.0.0
@date 2016-04-07
支持 NODE AMD BROWSER WORKER

### example

```html
<form>
    <select id="slc_province_1"></select>
    <select id="slc_city_1"></select>
</form>

<form>
    <select id="slc_province_2"></select>
    <select id="slc_city_2"></select>
</form>
```

```javascript
var loc_1 = new CityPicker(document.getElementById('slc_province_2'), 
                           document.getElementById('slc_city_2'),
                           '上海', '黄浦区');

var loc_2 = new CityPicker(document.getElementById('slc_province_3'), 
                           document.getElementById('slc_city_3'),
                           '重庆');

loc_1.getProvince()
// 上海
loc_1.getCity()
// 黄浦区
```


### API

##### CityPicker (constructor)

@param ele_province {Element} 省分 select 元素

@param ele_city {Element} 城市 select 元素,

@param province {[String]} default:false 默认的省份(省级市)，未传入则为“请选择”

@param city {[String]} default:false 默认的城市(市级区)，未传入则为“请选择”

@param error {[Function]} default:false 出错时的处理函数，参数为错误说明，默认直接throw

@param done {[Function]} default:false 省市都选择（非“请选择”选项）后触发的函数，参数为当前CityPicker对象，未传入则什么都不发生


### Error code

- missing argument: province: 初始化城市select的option时缺少对应的省份参数
- illegal province: 所选省份不在省份数据中
- 
