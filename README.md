# 自定义配置文件 train_custom.yaml
task: detect
mode: train
model: yolov8n.yaml
data: coco128.yaml
epochs: 300
imgsz: 640

# 增强参数优化
augment:
  hsv_h: 0.02
  translate: 0.15
  mosaic: 1.0
  mixup: 0.7
  close_mosaic: 10

# 训练策略
lr0: 0.01
lrf: 0.001
optimizer: Adam
cos_lr: True
amp: True
lr0: (1e-5, 1e-1)       # 初始学习率
weight_decay: (0.0, 0.001)  # 正则化强度
hsv_h: (0.0, 0.1)       # 色调扰动范围
