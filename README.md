# Flutter 列表（ListView.builder）

## 简介

生成 10 条字符串，用 **`ListView.builder`** 惰性构建 `ListTile`。最常见的长列表入门写法。

## 快速开始

### 环境要求

Flutter SDK。

### 运行

```bash
flutter pub get
flutter run
```

## 概念讲解

### 第一部分：`itemBuilder` 的职责

根据 `index` 返回一行；不要假设 builder 只调用一次，滚动时会反复触发，**勿在 builder 里做重计算或副作用**。

### 第二部分：分隔线与张紧

需要分隔时可换 `ListView.separated`；需要下拉刷新可外包 `RefreshIndicator`。

## 完整示例

见 `lib/main.dart`：`items` 列表与 `ListTile(title: ...)`。

## 注意事项

- 列表项含图片时请控制分辨率与缓存。
- 无限加载应在临近底部监听 `ScrollController`。

## 完整讲解（中文）

移动端列表＝ **Recycler 思想**：屏幕外的不画。`ListView.builder` 把这层帮你封好了。把它写顺后，再把「点击跳转、侧滑删除、骨架屏」逐一加上，就是日常 App 主列表。
