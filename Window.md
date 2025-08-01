### 1. 远程提示用户锁定

```shell
net user administrator /active:yes
```



### 2. 使用命令修改远程端口

- 设置 RDP 端口为 3389

```shell
Set-ItemProperty -Path "HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp" -Name "PortNumber" -Value 3389
```

- 放行 3389 端口（如果已存在不会报错）

```shell
New-NetFirewallRule -DisplayName "Allow RDP 3389" -Direction Inbound -Protocol TCP -LocalPort 3389 -Action Allow -Profile Any -EdgeTraversalPolicy Allow
```

- 重启远程桌面服务使设置生效（可能中断当前连接）

```shell
Restart-Service -Name TermService -Force
```



### 3. 计算机意外的重新启动或遇到错误,windows安装无法继续

- 按shift+F10出命令行窗口

- 输入regedit，找到注册表`HKEY_LOCAL_MACHINE --> SYSTEM --> SETUP --> STATUS --> ChildCompletion`，`ChildCompletion`下面有`SETUP.EXE`找到后双击它，将1修改为3即可，确定之后关闭注册表编辑器
- 点击错误消息框的确定，电脑就会自动重启，重新解析安装包再次进入安装系统。
