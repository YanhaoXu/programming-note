

-  使用Vscode运行命令时出现 __vsc_prompt_cmd_original: command not found

```shell
# 解决方法：
# 只需要在远程主机的.bashrc文件中添加一行命令unset PROMPT_COMMAND，然后保存文件退# 出后使用source ~/.bashrc 让更改生效。
# 下面在 远程主机（而不是本地主机） 上执行以上描述的具体步骤：
# 1.打开.bashrc文件
vi ~/.bashrc   # 使用Vim打开并编辑此文件
# 2.在该文件(.bashrc)中添加：
unset PROMPT_COMMAND
# 3.保存并退出文件，然后运行下面的命令使更改生效:
source ~/.bashrc # 
```

