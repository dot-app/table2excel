
# 介绍
json数据保存excel


# 安装
```
npm install git+https://github.com/dot-app/table2excel.git
```

# 用法
``` javascript
import table2excel from 'js-table2excel'

const column = [
	{
		title: 'Pic',
		type: 'image',
		width: 80,
		height: 50,
	},
	{ title: 'Name', bg: '#e2efda' },
	{ title: 'Nickname', bg: '#e2efda' },
	{ title: 'Mobile', bg: '#fce4d6' },
	{ title: 'Address', bg: '#fce4d6' },
]
const data = [
	{
		pic: {
			value: 'https://profile-avatar.csdnimg.cn/78fad80e6b8c40eb9da8ff5ca9697eb5_xunzaosiyecao.jpg!1',
			width: 80,
			height: 100
		},
		name: { value: 'xiao', rowspan: 3 },
		nickname: 'xiaoxiao',
		mobile: '1362500000',
		address: 'fujian xiamen',
	},
	{
		pic: 'https://profile-avatar.csdnimg.cn/78fad80e6b8c40eb9da8ff5ca9697eb5_xunzaosiyecao.jpg!1',
		name: 'xiao2',
		nickname: 'xiaoxiao2',
		mobile: '13625000002',
		address: 'fujian xiamen2',
	},
	{
		pic: 'https://profile-avatar.csdnimg.cn/78fad80e6b8c40eb9da8ff5ca9697eb5_xunzaosiyecao.jpg!1',
		name: 'xiao3',
		nickname: 'xiaoxiao3',
		mobile: '13625000003',
		address: 'fujian xiamen3',
	},
]
const excelName = 'boy'

table2excel(column, data, excelName)

```

# 参数说明

| 参数      |     简介     |
| :-------- | :----------: |
| column    |   head表头   |
| data      |   json数据   |
| excelName | 导出的文件名 |


## column
* title: 表头文字
* type: **text** / image
	* text: defalut
	* image: only accept start with http or https, and it can set image width and height
* other: 其他一些支持的配置属性，太简单了直接看demo吧


## data
* 键名：按照 Object 的索引位置和表头对应，键名只作为方便理解 (无需强制对应) 。
* 键值：如果是 Object 类型，取 Object.value作为键值，其他属性作为单元格配置选项（覆盖表头的配置）
* type: **text** / image
	* text: defalut
	* image: only accept start with http or https, and it can set image width and height

# todo
* 支持 colspan / rowspan

