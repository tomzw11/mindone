DIT过拟合测试用例

1. 准备数据集（以imagenet为例，单张图片，class label）
2. 过拟合训练启动指令

python train.py --config configs/training/class_cond_train.yaml --mode=1 --use_parallel=False --data_path=<PATH> --train_batch_size=1 --epochs=3000 --ckpt_save_interval=100 --ckpt_max_keep=1

3. 推理启动指令

python sample.py -c configs/inference/dit-xl-2-256x256.yaml --dit_checkpoint=<CKPT_PATH>
更新sample.py里面的class label（# Labels to condition the model with (feel free to change):）

4. 生成图片质量验证指令

python valid.py
