# 经验总结：EfficientNet-Lite0 水果分类上 GitHub

- **权重**：`runs/efficientnet_lite0/weights/best.pt` → `models/efficientnet_lite0_fruit_cls_best.pt`（约 14MB）  
- **推理**：timm `tf_efficientnet_lite0`，Actions 中需 **`pip install timm`**（与 torchvision-only 的 MobileNet/ShuffleNet 不同）  
- **姊妹仓**：[mobileNetV3large_backend](https://github.com/yhlkxkzs/mobileNetV3large_backend)、[ShuffleNetV2_fruitsclassify](https://github.com/yhlkxkzs/ShuffleNetV2_fruitsclassify)  
- **手机多仓上传**：本仓 `repo` 字段为 **`EfficientNet-Lite0_fruitsclassify`**（含连字符，API 路径需完全一致）
