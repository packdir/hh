
# 备份与恢复

备份：

    pg_dump dbname > dumpfile

上述命令是备份整个数据库，如果你只是想备份部分数据库内容，或者你只有部分内容权限，你可以使用下面的命令选项：

    -n schema
    -t table

恢复数据库之前，先创建一个新的数据库：

    createdb -T template0 newdb

然后导入：

    psql newdb < dumpfile


