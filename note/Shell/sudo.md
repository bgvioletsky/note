### 语法

```
sudo -V
sudo -h
sudo -l
sudo -v
sudo -k
sudo -s
sudo -H
sudo [ -b ] [ -p prompt ] [ -u username/#uid] -s
sudo command
```

**参数说明**：

- `-V` 显示版本编号
- `-h` 会显示版本编号及指令的使用方式说明
- `-l` 显示出自己（执行 sudo 的使用者）的权限
- `-v` 因为 sudo 在第一次执行时或是在 N 分钟内没有执行（N 预设为五）会问密码，这个参数是重新做一次确认，如果超过 N 分钟，也会问密码
- `-k` 将会强迫使用者在下一次执行 sudo 时问密码（不论有没有超过 N 分钟）
- `-b` 将要执行的指令放在背景执行
- `-p` prompt 可以更改问密码的提示语，其中 %u 会代换为使用者的帐号名称， %h 会显示主机名称
- `-u` username/#uid 不加此参数，代表要以 root 的身份执行指令，而加了此参数，可以以 username 的身份执行指令（#uid 为该 username 的使用者号码）
- `-s` 执行环境变数中的 SHELL 所指定的 shell ，或是 /etc/passwd 里所指定的 shell
- `-H` 将环境变数中的 HOME （家目录）指定为要变更身份的使用者家目录（如不加 -u 参数就是系统管理者 root ）
- `command` 要以系统管理者身份（或以 -u 更改为其他人）执行的指令