# 任意用户密码重置姿势

任意用户密码重置10钟常见姿势:
> https://mp.weixin.qq.com/s/_gSsw6W2d2EdFE2hmw-XoA
--------------------------------
## 姿势一 / 改url
/?step=a 改 /?step=b 直接跳到下一步
```angular2html
http://www.xxx.com/?step=a --> 直接改值跳到下一步 --> /?step=b
```
--------------------------------------------

## 姿势二 / 改返回包
> 前端校验后端未校验可能被绕过

- json格式返回包改为true
```
{
    status: false,
    message: error
}

```
改为 true

```
{
	status: true,
	message: success
}
```
-----------------------------------------------
## 姿势三 / 改用户id

> 不断抓包 每次修改返回包的参数, 使个人id变为别人的,导致任意用户密码重置
---------------------------------------------------
## 姿势四 / 遍历id
- 1.修改id值,越权修改他人密码
- 2.遍历number,获取所有_id
### 两者结合达到任意用户修改密码
在修改密码处 发现对原密码不存在检验 -> 即修改密码的数据包内没有原密码的值
```
{
	"_id": "283623473923403",
	"passwd": "123456"
}
```
原密码任意填写 都可以完成修改密码
### 打开思路, 在其他接口获取id, 达到任意修改密码

---------------------------------------------------------
