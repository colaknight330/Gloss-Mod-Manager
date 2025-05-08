# Tauri + Vue + TypeScript

这个模板可以帮助你开始使用Vue 3和TypeScript在Vite中进行开发。该模板使用Vue 3的`<script setup>` SFCs（单文件组件），查看[script setup文档](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup)了解更多信息。

## 推荐的IDE设置

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) + [Tauri](https://marketplace.visualstudio.com/items?itemName=tauri-apps.tauri-vscode) + [rust-analyzer](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer)

## 对`.vue`导入的TS类型支持

由于TypeScript无法处理`.vue`导入的类型信息，默认情况下它们被模拟为通用的Vue组件类型。在大多数情况下，如果你不太关心模板外的组件属性类型，这是没问题的。然而，如果你希望在`.vue`导入中获取实际的属性类型（例如，在使用手动`h(...)`调用时获取属性验证），你可以通过以下步骤启用Volar的接管模式：

1. 从VS Code的命令面板运行`Extensions: Show Built-in Extensions`，找到`TypeScript and JavaScript Language Features`，然后右键单击并选择`Disable (Workspace)`。默认情况下，如果默认的TypeScript扩展被禁用，接管模式将自动启用。
2. 通过从命令面板运行`Developer: Reload Window`重新加载VS Code窗口。

你可以在[这里](https://github.com/johnsoncodehk/volar/discussions/471)了解更多关于接管模式的信息。
