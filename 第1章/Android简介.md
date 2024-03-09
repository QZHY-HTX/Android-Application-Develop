# 课程仓库

- Github 注册并掌握 Git 工具使用
    - 安装 Git
    - 配置 Git 信息
        - git config --global user.name "xxx"
        - git config --global user.email "xxx@xxx.xxx"
        - ssh-keygen -t rsa -C "xxx@xxx.xxx"
        - ssh -T git@github.com
    - 如果遇到网络问题，请先考虑配置代理服务
        - git config http.sslVerify "false"
        - git config --global http.sslVerify "false"
        - git config --global http.proxy socks5 127.0.0.1:7890
        - git config --global https.proxy socks5 127.0.0.1:7890
        - git config --global http.proxy 127.0.0.1:7890
        - git config --global https.proxy 127.0.0.1:7890
    - 如果需要配置多个 Github 账号，请在 .ssh 中配置 config 文件，示例：
```
# test
Host test.github.com
Hostname github.com
IdentityFile ~/.ssh/id_rsa_test
User test
```

# Android 背景

# Android 特点

# Android 发展趋势

# MacMini Test