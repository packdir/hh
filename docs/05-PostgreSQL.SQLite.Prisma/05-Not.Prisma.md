
当要 Join 查询时，我花了一个小时，仍然不知道如何实现。我在定义 airoom 表时，并没有定义多表关系，因此无法使用 include 方法。直到我看到下面这篇文章，才知道别人也发现这个问题，大受震惊：

[We migrated to SQL. Our biggest learning? Don’t use Prisma](https://codedamn.com/news/product/dont-use-prisma)

首先，Prisma schema 仍然是好东西，可以继续使用。

There is no concept of SQL-level joins in Prisma. This was one of the most shocking revelations to us. In some queries we inspected that supposedly should have used SQL Joins or subqueries, we discovered that at a low level, Prisma was fetching data from both tables and then combining the result in its “Rust” engine. This was a path for an absolute trash performance.






