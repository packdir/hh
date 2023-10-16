

## 只显示文件名

仅仅显示差异文件的文件名：

    diff -rq dir1 dir2

查看man，关于 -q 的解释：

    -q, --brief
        report only when files differ

## 排除目录或文件

排除目录：

    diff -r --exclude="node_modules" dir1 dir2

排除文件：

    diff -r --exclude="FILENAME" dir1 dir2


