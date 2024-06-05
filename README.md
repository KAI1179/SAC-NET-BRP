# SAC_NET_BRP

Reference this [repo](https://github.com/KaihuaTang/Scene-Graph-Benchmark.pytorch) for environmental configuration and dataset preparation


```bash
 # train motifs + BPR(RW):
python tools\relation_train_net.py CUDA_VISIBLE_DEVICES=0 --config-file "configs/e2e_relation_X_101_32_8_FPN_1x.yaml" MODEL.ROI_RELATION_HEAD.USE_GT_BOX True MODEL.ROI_RELATION_HEAD.USE_GT_OBJECT_LABEL True MODEL.ROI_RELATION_HEAD.PREDICTOR MotifPredictor SOLVER.IMS_PER_BATCH 12 TEST.IMS_PER_BATCH 1 DTYPE "float16" SOLVER.MAX_ITER 50000 SOLVER.VAL_PERIOD 2500 SOLVER.CHECKPOINT_PERIOD 2500 GLOVE_DIR YOUR_GLOVE_PATH MODEL.PRETRAINED_DETECTOR_CKPT YOUR_FASTER_RCNN_PATH/pretrained_faster_rcnn/model_final.pth OUTPUT_DIR ./output/motifs-brp-rw-precls
```

```bash
 # train SAC-Net + BPR(RW):
python tools\relation_train_net.py CUDA_VISIBLE_DEVICES=0 --config-file "configs/e2e_relation_X_101_32_8_FPN_1x.yaml" MODEL.ROI_RELATION_HEAD.USE_GT_BOX True MODEL.ROI_RELATION_HEAD.USE_GT_OBJECT_LABEL True MODEL.ROI_RELATION_HEAD.PREDICTOR SACMPredictor SOLVER.IMS_PER_BATCH 12 TEST.IMS_PER_BATCH 1 DTYPE "float16" SOLVER.MAX_ITER 50000 SOLVER.VAL_PERIOD 2500 SOLVER.CHECKPOINT_PERIOD 2500 GLOVE_DIR YOUR_GLOVE_PATH MODEL.PRETRAINED_DETECTOR_CKPT YOUR_FASTER_RCNN_PATH/pretrained_faster_rcnn/model_final.pth OUTPUT_DIR ./output/SACNET-brp-rw-precls
```

More detailed instructions will be released later
