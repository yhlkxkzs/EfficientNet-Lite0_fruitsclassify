# 移动端与 GitHub 对接说明（EfficientNet-Lite0）

与 **ShuffleNetV2_fruitsclassify** / **mobileNetV3large_backend** 流程相同：OAuth → **Contents API** → `incoming/` → Actions 推理。

## 1. 本仓库约定

| 项 | 值 |
|----|-----|
| 仓库 | `yhlkxkzs/EfficientNet-Lite0_fruitsclassify` |
| 分支 | `main` |
| 权重 | `models/efficientnet_lite0_fruit_cls_best.pt` |
| Workflow | `Fruit classification (EfficientNet-Lite0)` |

## 2. PUT 示例路径

```http
PUT https://api.github.com/repos/yhlkxkzs/EfficientNet-Lite0_fruitsclassify/contents/incoming/{filename}
```

## 3. 可选服务器转发

Secrets：`FRUIT_SERVER_UPLOAD_URL`、`FRUIT_SERVER_UPLOAD_TOKEN`；表单字段 `repo` 为本仓库全名。

## 4. 多模型 App

在 `uploadTargets` 中增加一项：`owner: yhlkxkzs`，`repo: EfficientNet-Lite0_fruitsclassify`（注意仓库名含连字符）。
