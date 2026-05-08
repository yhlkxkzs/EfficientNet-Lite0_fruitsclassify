# EfficientNet-Lite0_fruitsclassify

GitHub 侧用于存放**水果分类**推理权重（**EfficientNet-Lite0**，timm：`tf_efficientnet_lite0`），供 Actions 或本地脚本拉取使用。

**移动端对接**：**[docs/MOBILE_APP_INTEGRATION.md](docs/MOBILE_APP_INTEGRATION.md)**  
**经验总结**：**[docs/EXPERIENCE_GITHUB_EFFICIENTNET_LITE0.md](docs/EXPERIENCE_GITHUB_EFFICIENTNET_LITE0.md)**  
可选 **Actions POST 图片到自建服务**：Secrets `FRUIT_SERVER_UPLOAD_URL` / `FRUIT_SERVER_UPLOAD_TOKEN`（与其它水果模型仓同名，接收端用 `repo` 区分）。

## 依赖

推理需 **timm**（与训练一致）：

```bash
pip install torch torchvision timm pillow
```

## 当前权重

| 文件 | 说明 |
|------|------|
| `models/efficientnet_lite0_fruit_cls_best.pt` | checkpoint（`model_type: efficientnet_lite0`） |

- **类别**：见 `models/classes.json`  
- **来源**：`runs/efficientnet_lite0/weights/best.pt` 复制。

## 加载示例（Python）

```python
import torch
import timm

ckpt = torch.load("models/efficientnet_lite0_fruit_cls_best.pt", map_location="cpu", weights_only=False)
model = timm.create_model("tf_efficientnet_lite0", pretrained=False, num_classes=ckpt["num_classes"])
model.load_state_dict(ckpt["model_state_dict"])
model.eval()
```

## 克隆

```bash
git clone git@github.com:yhlkxkzs/EfficientNet-Lite0_fruitsclassify.git
```

## GitHub Actions

向 **`incoming/`** push 图片或手动 **Run workflow** → **Fruit classification (EfficientNet-Lite0)** → Artifacts **`predictions`**。

## 本地推理

```bash
pip install torch torchvision timm pillow
python scripts/infer_fruit.py
```

输出默认：`output/predictions.json`（已 `.gitignore`）。
