


在 Ubuntu 上安装 PostgreSQL：

    sudo apt install postgresql postgresql-contrib


提示重启服务，接受默认值就可以了。

切换用户：

    sudo -i -u postgres

使用命令行：

    psql

查看全部数据库：

    \l

查看当前连接到哪个数据库：

    \conninfo

退出命令行：

    \q

查看 PostgreSQL 版本：

    psql --verions
    // 或者
    psql -V


## 创建用户及数据库

PG 的规则是：系统用户名、PG 用户名、数据库名三者一致。因此，下面依次创建这三者：


### 创建系统用户

创建 Ubuntu 用户：

    sudo adduser aishell


### 创建 PG 用户

使用 postgres 用户来创建新用户 aishell。在 PostgreSQL 中，用户也称为角色（Role）:

    sudo -i -u postgres
    createuser --interactive


### 修改用户密码

使用 postgres 用户登录 psql，然后使用下面的命令修改密码：

    \password aishell




