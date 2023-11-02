

[What is the difference between res.end() and res.send()?](https://stackoverflow.com/questions/29555290/what-is-the-difference-between-res-end-and-res-send)

## send() 之后如果还有代码

为了终止 send() 执行之后继续执行后面的代码，需要使用 return：

```
if (some condition) {
     res.send(...);
     return;
}

// some other code
res.send(...);
```

来源：[Should I return explicitly after res.send in Express?](https://stackoverflow.com/a/75972397/3054511)


