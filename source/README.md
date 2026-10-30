# 简记源码

简记 0.3.3 的可审阅源码包：

- [简记-源码-0.3.3.zip](./简记-源码-0.3.3.zip)
- [简记-源码-0.3.2.zip](./简记-源码-0.3.2.zip)
- [简记-源码-0.3.1.zip](./简记-源码-0.3.1.zip)
- [简记-源码-0.3.0.zip](./简记-源码-0.3.0.zip)

0.3.3 优化了账页快捷指令入口、分类统计明细和设置页信息层级，同时保留 OCR 懒加载、Muse 接口与干净发布流程。

## Muse 权限

- read：查询账目和分类
- write：创建账目
- update：修改 Muse 创建的账目
- delete：删除 Muse 创建的账目

手工账目不会被 Muse 修改或删除。

## 构建

```powershell
npm ci
npm run build
npm run publish:pages -- --target C:\path\to\repo\jianji
```

Tesseract wasm 和语言包不重复放入源码包；首次构建前从部署目录的 `jianji/tesseract`、`jianji/tessdata` 复制到源码项目的 `public/`。发布脚本会先带入并校验这些运行资源，再清空旧 `jianji/`。