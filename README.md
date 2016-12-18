# 获取国内IP及路由表

首先获取国内IP及路由表：
1.不想自己生成的可以直接下载cnIP目录内的文件

2.从 http://ftp.apnic.net/apnic/stats/apnic/delegated-apnic-latest 获取 delegated-apnic-latest.txt

将文件拖进getcnIP.exe 

或使用命令 getcnIP.exe +文件名

或将文件放进getcnIP.exe同目录后双击getcnIP.exe

## Windows
__delegated-apnic.txt__：

直接放进ShadowsocksR目录内,PAC选择"绕过大陆IP"

__add.txt__：

使用以下bat添加路由表，与[cmroute.dll](https://github.com/HMBSbige/getcnIP/releases/download/1.0/cmroute.dll)同目录
```
@echo off

net session >nul 2>&1
if not %errorlevel% == 0 (
  echo 请使用右键 "已管理员身份运行" 此脚本
  pause
  exit 1
)

cd /d %~dp0
echo 导入路由表...
rundll32.exe cmroute.dll,SetRoutes /STATIC_FILE_NAME add.txt /DONT_REQUIRE_URL /IPHLPAPI_ACCESS_DENIED_OK
pause
```
__del.txt__：

使用以下bat删除路由表，与[cmroute.dll](https://github.com/HMBSbige/getcnIP/releases/download/1.0/cmroute.dll)同目录
```
@echo off

net session >nul 2>&1
if not %errorlevel% == 0 (
  echo 请使用右键 "已管理员身份运行" 此脚本
  pause
  exit 1
)

cd /d %~dp0
echo 移除路由表...
rundll32.exe cmroute.dll,SetRoutes /STATIC_FILE_NAME del.txt /DONT_REQUIRE_URL /IPHLPAPI_ACCESS_DENIED_OK
pause
```

注：重启后自动清空路由表
## Linux
看心情添加
## Mac os x
看心情添加
