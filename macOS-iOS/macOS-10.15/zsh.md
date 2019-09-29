在 Mac 上将 zsh 用作默认 Shell

```
The default interactive shell is now zsh.
To update your account to use zsh, please run `chsh -s /bin/zsh`.
For more details, please visit https://support.apple.com/kb/HT208050.
```

# 配置 

查看当前环境shell:

```
echo $SHELL
```

查看系统自带哪些shell:

```
cat /etc/shells
```

将zsh设置为默认shell

```
chsh -s /bin/zsh
```
