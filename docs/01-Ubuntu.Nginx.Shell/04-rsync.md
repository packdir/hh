

rsync 可以用于本地及远程拷贝文件。

rsync 的优势在于：

- 高效的文件传输

  rsync 使用增量传输算法，这意味着它只传输源文件和目标文件之间的差异，这显着减少了传输的数据量，使其能够高效地同步大文件或目录。

- 远程文件同步

  rsync 支持通过 SSH 进行本地和远程文件传输，这允许本地和远程系统之间或跨多台计算机的镜像目录之间的同步。

- 增量备份

  rsync 非常适合增量备份，因为它通过仅传输新的或修改的文件来有效地创建和更新备份。

- 保留文件权限

  rsync 可以保留各种文件属性，例如权限、所有权、时间戳和符号链接，这确保复制的文件在目标上保留其原始特征。

- 带宽控制

  rsync 允许您限制文件传输期间的带宽使用，因为它在两端发送和接收数据时使用压缩和解压缩方法。

- 更快

  在传输文件方面，rsync 比 scp（安全复制）更快，尤其是在同步大型目录或处理已部分传输或存在于目标上的文件时。


命令格式：

    rsync [OPTION...] SRC... [DEST]

常用参数：

-v – 详细输出，显示有关传输的详细信息。
-r – 递归复制数据（但在传输数据时不保留时间戳和权限。
-a – 存档模式，允许递归复制文件，并且还保留符号链接、文件权限、用户和组所有权以及时间戳。

排除目录：

    rsync --exclude "node_modules" SOURCE DESTINATION


## 参考

[16 Rsync Command Examples for Efficient File Synchronization](https://www.tecmint.com/rsync-local-remote-file-synchronization-commands/)



