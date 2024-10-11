# Super-Resolution Algorithm Template 🚀

This project is a **super-resolution algorithm template** built on **PyTorch Lightning 2.0+**, supporting **distributed training** and integrating various **logging functionalities**, such as **Wandb**. With this template, you can quickly build and train your own super-resolution models, making high-resolution image generation easier!

This project is a modification and extension of the [**miracleyoo/pytorch-lightning-template**](https://github.com/miracleyoo/pytorch-lightning-template) repository. We inherited the excellent design from the original repository and further optimized and enhanced it, especially for super-resolution tasks.

## Highlights ✨

- **Built with PyTorch Lightning 2.0**: A highly efficient and flexible deep learning training framework that simplifies the training process.
- **Super-resolution task support**: Specifically designed for image super-resolution, supporting custom super-resolution models.
- **Distributed training**: Supports multi-GPU distributed training, allowing you to easily leverage large-scale computational resources.
- **Wandb and other logging integrations**: Integrated with **Wandb** and other common loggers to track various metrics and hyperparameters during training for easy visualization and monitoring.
- **Easy-to-use template**: Whether for research experiments or production deployment, you can quickly modify this template to fit your model and dataset!

## Quick Start 🏃‍♂️

### 1. Clone the repository

First, clone this project:

```bash
git clone https://github.com/RuixuanYing/Super-resolution-lightning.git
cd super-resolution-template
```

### 2. Install dependencies

Use `pip` to install the necessary dependencies:

```bash
pip install -r requirements.txt
```

### 3. Configure and train the model

You can specify training hyperparameters via the command line:

```bash
python train.py --batch_size 16 --max_epochs 100 --gpus -1 --accelerator gpu
```

If you want to use distributed training, simply add the `--strategy ddp` flag:

```bash
python train.py --batch_size 16 --max_epochs 100 --gpus 4 --accelerator gpu --strategy ddp
```

By default, **Wandb** is integrated, and all training logs and model performance will be automatically recorded once training starts. If you haven’t logged into Wandb yet, run the following command first:

```bash
wandb login
```

### 4. Customize your super-resolution model

In `model.py`, you can define your own super-resolution network structure. You just need to inherit from `pl.LightningModule` and implement your `forward` and `training_step` logic, and Lightning will handle the rest!

### 5. Logging and monitoring

- This project integrates **WandbLogger**, which automatically tracks various metrics during training, including PSNR, SSIM, and more. You can view real-time training progress at `wandb.ai`.

## Project Structure 🗂️

```bash
super-resolution-template/
│
├── data/                    # data
│   ├── __init__.py
│   ├── common.py
│   ├── data_interface.py
│   ├── recursive_up.py
│   └── satup_data.py
│
├── model/                   # model
│   ├── __init__.py
│   ├── common.py
│   ├── fsrcnn.py
│   ├── metrics.py
│   ├── model_interface.py
│   ├── rdn_fuse.py
│   └── utils.py
│
├── .gitignore                # Git ignore
├── LICENSE                   # liecense
├── main.py                   # train_main
├── README.md                 # readme
└── utils.py                  # sometools
```

## Future Plans 🛠️

- [ ] Add more pretrained model support, such as EDSR, RCAN, etc.
- [ ] Integrate more logging tools like TensorBoard and Neptune.
- [ ] Extend support for various super-resolution tasks, including single image SR, video SR, etc.

## Contribution Guide 🤝

Contributions are welcome! Feel free to submit PRs or Issues to improve this template. If you have any questions or suggestions, don’t hesitate to let me know! 😄

1. Fork this repository
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -am 'Add some amazing feature'`)
4. Push to your branch (`git push origin feature/amazing-feature`)
5. Create a Pull Request

## Acknowledgments 🙌

A big thank you to [**miracleyoo/pytorch-lightning-template**](https://github.com/miracleyoo/pytorch-lightning-template) for providing the excellent code template! This project builds upon that foundation with modifications and optimizations, with special thanks to their contributions to the PyTorch Lightning community.

---

Let’s build some amazing super-resolution models together! 🎉

