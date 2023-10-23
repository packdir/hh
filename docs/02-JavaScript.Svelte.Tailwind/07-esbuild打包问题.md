
在 wsl 下开发，svelte 使用：

    <script lang="ts">

提示错误，esbuild 打包平台与当前平台不一样。解决办法是，到 Windows 系统下进行安装（npm i），然后将 node_modules/@esbuild/win32-x64 拷贝到 wsl 下的对应目录。

这样在 node_modules/@esbuild 目录下就存在两个子目录：

- linux-x64
- win32-x64


