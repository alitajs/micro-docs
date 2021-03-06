# Device

## 获取原生参数
```js
    cons res = await alita.device.getUserData();
```
### 参数
无
### 响应
**Object res**

## 扫码解析
```js
    const res = await alita.device.scanCode(params);
```
### 参数
**Object params**

| 属性 | 类型 | 默认值 | 必填 | 说明 |
| :- | :- | :- | :- | :- |
| onlyFromCamera | boolean | false | 否 | 是否只能从相机扫码，不允许从相册选择图片 |
| scanType | Array<string\> | ['qrCode'] | 否 | 扫码类型，目前只支持二维码 |

### 响应
**Object res**

| 属性 | 类型 | 说明 |
| :- | :- | :- |
| result | string | 所扫码的内容 |

## 获取系统信息
```js
const res = await alita.device.systemInfo();
```
### 参数
### 响应
**Object res**

| 属性 | 类型 | 说明 |
| :- | :- | :- |
| platform | string | `ios` or `android` |
| version | string | 主app版本，如1.0.0 |
| uuid | string | 设备唯一标识 |
| statusBarHeight | number | 导航栏高度 |
| SDKVersion | string | 微应用基础库版本号，如1.0.0 |

## 打开web页面
```js
alita.device.openWeb(url: string)
```
### 参数
**String url**

| 属性 | 类型 | 说明 |
| :- | :- | :- |
| url | string | 要打开的URL |

### 响应
无

## 获取微应用列表
```js
const res = await alita.device.fetchMicroAppList();
```
### 参数
无
### 响应
**Array<`MicroApp`\> res**

`MicroApp`: 微应用对象

| 属性 | 类型 | 说明 |
| :- | :- | :- |
| appid | string | 微应用唯一标识 |
| appsecret | string | 微应用 `appsecret` |
| appName | string | 微应用名称 |
| appDesc | string | 微应用描述 |
| appIconUrl | string | 微应用缩略图链接 |
| versionId | string | 微应用版本 id |

## 打开微应用
```js
const res = await alita.device.openMicroApp(params);
```
### 参数
**Object params**

| 属性 | 类型 | 默认值 | 必填 | 说明 |
| :- | :- | :- | :- | :- |
| app | `MicroApp` | 无 | app 或 appURL 必传其一 | 要打开的微应用对象 |
| appURL | string | 无 | app 或 appURL 必传其一 | 要打开的微应用链接 |
| userData | object | 无 | 否 | 传给要打开微应用的参数 |

## 查询安装的地图

```js
const res = await alita.device.mapsList();
```

### 参数
无

### 响应
无

**Array<Map\>** res

`Map`: 地图对象

| 属性 | 类型 | 说明 |
| :- | :- | :- |
| type | string | `baidu` \| `amap` \| `apple` \| `google` \| `qq` |

### 配置

`iOS` 需要在 `Info.plist` 中的 `LSApplicationQueriesSchemes` 加下面几个 URLScheme

- baidumap
- iosamap
- comgooglemaps
- qqmap


## 打开 URLScheme

```js
alita.device.openURLScheme(params: { url: string });
```

### 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 |
| :- | :- | :- | :- | :- |
| url | string | 无 | 是 | 要打开的`URLSchema` |

### 响应

无

## 关闭当前微应用

> `alita-micro` >= 0.3.0  
> iOS: `AlitaNativeLib` >= 0.6.0  
> android: `micro-app-android-framework` >= 1.0.32  

```js
alita.device.closeMicroApp()
```

## 参数

无

## 响应

无