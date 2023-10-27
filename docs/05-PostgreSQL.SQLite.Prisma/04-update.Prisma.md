
同时升级两个包：

    Update available 4.13.0 -> 5.5.2                       │
                                                         │
    This is a major update - please follow the guide at    │
    https://pris.ly/d/major-version-upgrade                │
                                                         │
    Run the following to update                            │
      npm i --save-dev prisma@latest                       │
      npm i @prisma/client@latest

升级的同时，删除了一个字段（info），结果出现这个错误：

```
src/prisma.service.ts:12:14 - error TS2345: Argument of type 'string' is not assignable to parameter of type 'never'.                                                                                                                                                                                    12     this.$on('beforeExit', async () => {                                                                        ~~~~~~~~~~~~                                                                                                                                                                          Found 1 error(s).
```

未找到原因，暂时解决办法是注释掉这段出问题的代码：

```
-  async enableShutdownHooks(app: INestApplication) {
-    this.$on('beforeExit', async () => {
-      await app.close();
-    });
-  }
+  //async enableShutdownHooks(app: INestApplication) {
+  //  this.$on('beforeExit', async () => {
+  //    await app.close();
+  //  });
+  //}
 }
```

