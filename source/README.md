# 简记源码

简记 0.3.0 的可审阅源码包位于：

- [简记-源码-0.3.0.zip](./简记-源码-0.3.0.zip)

源码包包含：

- React / TypeScript 页面和业务逻辑
- OCR 懒加载与图像预处理
- PWA 与 Service Worker 构建配置
- Supabase 表结构、RLS、RPC 函数
- Muse 单密钥 Edge Function
- 清理旧 assets 的发布脚本
- 产品与设计说明

## 构建

```powershell
npm ci
npm run build
npm run publish:pages -- --target C:\path\to\repo\jianji
```

Tesseract wasm 和语言包体积较大，不重复放入源码包；构建前从部署目录的 `jianji/tesseract`、`jianji/tessdata` 复制到源码项目的 `public/`。

## 部署约定

`jianji/` 只保存编译产物。每次发布前由 `publish:pages` 清空并重建，避免旧 assets 和旧 Service Worker 文件持续堆积。

## 版本

- 0.3.0：分类合并修复、支付方式筛选、商家搜索、月度趋势、分类预算提醒、OCR 懒加载。
