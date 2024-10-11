# 超分辨率算法模板 🚀

这个项目是一个基于 **PyTorch Lightning 2.0** 的超分辨率算法模板，支持**分布式训练**，并且集成了各种**日志记录功能**，比如 **Wandb**。通过这个模板，你可以快速构建和训练自己的超分辨率模型，让高分辨率图像的生成变得更加轻松！

本项目是对 [**miracleyoo/pytorch-lightning-template**](https://github.com/miracleyoo/pytorch-lightning-template) 仓库的修改和扩展。我们继承了原仓库的优秀设计，并做了进一步的优化和增强，特别是在超分辨率任务上的适配。

## 项目亮点 ✨

- **PyTorch Lightning 2.0 构建**：高效、灵活的深度学习训练框架，简化模型训练流程。
- **超分辨率任务支持**：专为图像超分辨率设计，支持自定义超分辨率模型。
- **分布式训练**：支持多 GPU 分布式训练，让你轻松利用大规模计算资源。
- **Wandb 等日志集成**：支持 **Wandb** 和其他常用 logger，记录训练过程中的各种指标和超参数，方便可视化监控。
- **简单易用的模板**：不论是用于实验还是产品落地，直接在这个模板基础上修改你的模型和数据集即可！

## 快速开始 🏃‍♂️

### 1. 克隆仓库

首先，克隆本项目：

```bash
git clone https://github.com/yourusername/super-resolution-template.git
cd super-resolution-template
```

### 2. 安装依赖

使用 `pip` 安装所需的依赖：

```bash
pip install -r requirements.txt
```

### 3. 配置和训练模型

你可以通过命令行指定训练的超参数：

```bash
python train.py --batch_size 16 --max_epochs 100 --gpus -1 --accelerator gpu
```

如果你想使用分布式训练，只需添加 `--strategy ddp` 即可：

```bash
python train.py --batch_size 16 --max_epochs 100 --gpus 4 --accelerator gpu --strategy ddp
```

默认集成了 Wandb，开始训练时会自动记录所有的训练日志和模型表现。如果你还没有登录 Wandb，请先运行以下命令：

```bash
wandb login
```

### 4. 自定义你的超分辨率模型

在 `model.py` 中可以定义你自己的超分辨率网络结构。你只需要继承 `pl.LightningModule` 并实现你的 `forward` 和 `training_step` 逻辑，剩下的工作 Lightning 会帮你处理！

### 5. 日志与监控

- 本项目集成了 **WandbLogger**，可以自动记录训练过程中的各种指标，包括 PSNR、SSIM 等。你可以通过 `wandb.ai` 网站实时查看训练进度。
- 你也可以通过修改 `config.yaml` 文件中的 `logger` 相关配置，启用不同的日志记录器（如 TensorBoard）。

## 文件结构 🗂️

```bash
super-resolution-template/
│
├── config/                  # 配置文件
├── data/                    # 数据模块
├── models/                  # 模型文件，定义了超分辨率算法的网络结构
├── logs/                    # 日志文件目录
├── utils/                   # 一些工具函数
├── train.py                 # 训练入口
├── requirements.txt         # 依赖文件
└── README.md                # 本文档
```

## 未来计划 🛠️

- [ ] 增加更多预训练模型支持，如 EDSR、RCAN 等。
- [ ] 集成更多日志记录工具，如 TensorBoard 和 Neptune。
- [ ] 增加对多种超分辨率任务的支持，包括单图像超分、视频超分等。

## 贡献指南 🤝

欢迎大家提交 PR 或 Issue 来改进这个模板！如果你有任何问题或者建议，别忘了告诉我！😄

1. Fork 本仓库
2. 创建一个新的分支 (`git checkout -b feature/amazing-feature`)
3. 提交你的改动 (`git commit -am 'Add some amazing feature'`)
4. 推送到你的分支 (`git push origin feature/amazing-feature`)
5. 创建一个 Pull Request

## 致谢 🙌

感谢 [**miracleyoo/pytorch-lightning-template**](https://github.com/miracleyoo/pytorch-lightning-template) 提供的优秀代码模板！本项目在此基础上进行了修改和优化，特别感谢其对 PyTorch Lightning 社区的贡献。

---

快来一起训练一些令人惊叹的超分辨率模型吧！🎉


