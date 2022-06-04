# TransRLUNet

An incremental study on RLUNet. I replace RLUNet’s 1*1 Conv in Feature Fusion(Features concatenated from decoders to encoders) with a standard Transformer layer in the Encoders of RLUNet, expecting that Transformer can better fuse the features into halfed channels. However, this experiment failed. No matter how I adjust the parameters the TransRLUNet just cannot converge. If you look at the log.txt in this Repo you will find that after the 3rd Epoch the loss and validation performances have never changed ever since. The reason is still in investigation. If I have any findings I will report to this Github channel of mine. You are welcomed to follow my channel. If you can give me some stars and thumb ups to support my research it will be very much appreciated.

Illustrations for the use of this repository:

1, data preparation and training

First download GoPro dataset for training on GoPro's official site and run training command in below:

python3 ./train.py --arch Uformer --gpu '0,1,2,3,4,5,6,7' --train_ps 128 --train_dir ../GoPro/train --val_dir ../GoPro/test --embed_dim 16 --warmup --batch_size 64 --lr_initial 0.002 --nepoch 500

3, test and pretrained models

My originally pretrained weights will not be supplied here. When you have finished your own training, use your .pth files in the test.py scripts

If you want to use this repo for any academic or commercial purpose or if you have any questions to ask me please contact me in shengyuan_yan@163.com and for academic references please cite TransRLUNet as followings:

Shengyuan Yan. Research on Image Restoration Method based on Local Self-attention Mechanism[M]. Wuhan University, China, 2022.

Thanks for your attention and starring
