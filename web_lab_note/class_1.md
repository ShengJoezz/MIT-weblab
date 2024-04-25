
<<<<<<< HEAD
=======
| 命令                        | 用法说明                                                     |
| --------------------------- | ------------------------------------------------------------ |
| `cd <directory>`            | 切换到指定目录                                               |
| `ls`                        | 列出当前目录下的文件和子目录                                 |
| `ls -a`                     | 列出当前目录下的所有文件和子目录(包括隐藏文件)               |
| `ls -l`                     | 以长格式列出当前目录下的文件和子目录(包括权限、所有者等信息) |
| `mkdir <directory>`         | 创建新的目录                                                 |
| `rmdir <directory>`         | 删除空目录                                                   |
| `rm <file>`                 | 删除文件                                                     |
| `rm -r <directory>`         | 递归删除目录及其下的所有文件和子目录                         |
| `mv <source> <destination>` | 移动或重命名文件/目录                                        |
| `cp <source> <destination>` | 复制文件/目录                                                |
| `cat <file>`                | 查看文件内容                                                 |
| `less <file>`               | 分页查看文件内容                                             |
| `man <command>`             | 查看命令的手册页                                             |
| `pwd`                       | 显示当前工作目录的完整路径                                   |
| `clear`                     | 清除终端屏幕内容                                             |
| `exit`                      | 退出当前终端会话                                             |
| `sudo <command>`            | 以超级用户身份执行命令                                       |
| `apt update`                | 更新软件包列表(Ubuntu/Debian)                                |
| `apt upgrade`               | 升级已安装的软件包(Ubuntu/Debian)                            |
| `apt install <package>`     | 安装新的软件包(Ubuntu/Debian)                                |

我在使用wsl中，想要利用`git push origin main`，但是出现了一些没有遇到的问题，记录在下：

# Git在Linux和Windows上的差异

Git作为分布式版本控制系统,在不同操作系统上的使用体验会有一些差异。本文档将重点介绍Git在Linux和Windows上使用时的一些区别。

## 配置方面

### Windows

- 在Windows上,Git通常会在初次安装时自动进行一些合理的默认配置,例如设置用户名和email等。

### Linux

- 在Linux系统上,大多数发行版在安装Git时通常不会进行初始化配置,需要用户自己使用`git config`命令进行设置,例如:

  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your@email.com"
  ```

## 身份验证方式

### Windows

- 在Windows上,Git通常使用操作系统的凭据管理器来存储和管理GitHub的身份验证信息,无需在每次推送时输入凭据。

### Linux

- 在Linux上,Git无法直接访问这些凭据管理器,所以在推送(push)代码到GitHub时,需要使用以下方式进行身份验证:
  - 输入GitHub的用户名和密码(已弃用,不推荐)
  - 使用SSH密钥
  - 使用个人访问令牌(Personal Access Token)

示例:

```bash
# 使用SSH密钥
git push origin main

# 使用个人访问令牌
Username: your_github_username
Password: your_personal_access_token
```

## 拉取(pull)操作

### Windows

- 在Windows上,Git通常默认使用`git pull`时的`--ff-only`或`--rebase`选项来保持线性的提交历史。

### Linux  

- 在Linux上,默认的`git pull`行为是创建一个合并提交,导致提交历史存在分支。所以需要额外配置`pull.rebase`选项来定制拉取操作的行为。

  ```bash
  # 配置为使用rebase模式进行pull
  git config --global pull.rebase true

  # 配置为使用merge模式进行pull (默认行为)
  git config --global pull.rebase false
  ```

总的来说,Linux上使用Git需要更多的手动配置和管理,而Windows上Git在安装时就为您做了很多自动化的合理默认配置,使得在Windows上使用Git的体验通常更加简单直观一些。但同时Linux也给予了用户更多的定制化选择。这些差异源于Linux和Windows操作系统本身的差异所导致的。

也就是说，`git config`在Windows和Linux上是不一样的，要注意区分。
