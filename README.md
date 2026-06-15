# Resource-Aware DETR: Dynamic Computation Scheduling for Highly Heterogeneous Remote Sensing Scenes
<img width="734" height="175" alt="image" src="https://github.com/user-attachments/assets/4e78ceeb-49f3-4865-ae63-9eaa269e064f" />

## Core Contributions
1. The FG-SMoE integrates frequency and spatial priors to adaptively purify multi-scale features, enhance faint target representations, and suppress background clutter.
2. The lightweight FG-Block combines dynamic convolution and window-based self-attention to collaboratively encode local details and global context with low computational cost.
3. The proposed FG-FPN mitigates small-target feature dilution and detail degradation during cross-scale fusion and effectively strengthens the feature representation of weak targets.
4. The WM-DQM dynamically allocates decoder queries by perceiving scene density, eliminating fixed-query-induced computational redundancy and dense-target misses while avoiding structural dependence in traditional dynamic query designs.

## Experimental Results
### Results on AI-TODv2 Dataset
| Methods | AP50 | AP75 | AP | APs | APm | APl | Flops |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| YOLO11s | 30.3 | 9.9 | 13.2 | 12.5 | 27.7 | - | 21.3 |
| YOLO11m | 34.1 | 11.8 | 15.3 | 31.7 | 14.4 | - | 67.7 |
| YOLO12s | 29.3 | 9.3 | 12.8 | 12.4 | 26.8 | - | 19.3 |
| YOLO12m | 33.4 | 10.8 | 14.7 | 13.9 | 30.0 | - | 60.1 |
| YOLO13s | 29.9 | 8.8 | 12.6 | 12.0 | 25.6 | - | 20.1 |
| YOLO13l | 34.0 | 11.8 | 15.3 | 14.4 | 31.4 | - | 84.4 |
| Hyper-YOLOs | 32.1 | 10.4 | 14.0 | 13.3 | 28.7 | - | 33.8 |
| Hyper-YOLOm | 35.0 | 11.7 | 15.6 | 14.8 | 31.1 | - | 91.8 |
| RT-DETR-r18 | 33.6 | 10.1 | 14.3 | 13.7 | 26.2 | - | 57.0 |
| RT-DETR-r34 | 34.5 | 10.3 | 14.7 | 13.9 | 27.0 | - | 88.8 |
| RT-DETRv2-r18 | 40.1 | 12.7 | 17.6 | 16.9 | 28.1 | - | 59.9 |
| RT-DETRv2-r34 | 41.2 | 12.7 | 17.9 | 17.2 | 29.9 | - | 91.9 |
| D-FINE-s | 36.7 | 12.6 | 16.7 | 16.0 | 27.9 | - | 24.9 |
| D-FINE-m | 39.5 | 13.7 | 17.9 | 17.2 | 29.8 | - | 56.4 |
| Deim-DFINE-s | 36.3 | 12.3 | 16.3 | 15.6 | 26.9 | - | 24.9 |
| Deim-DFINE-m | 38.3 | 12.6 | 17.1 | 16.4 | 28.9 | - | 56.4 |
| **RA-DETR** | **49.5** | **16.5** | **22.2** | **21.5** | **36.9** | - | **38.6** |

### Results on VisDrone2019 Dataset
| Methods | AP50 | AP75 | AP | APs | APm | APl | Flops |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| YOLO11s | 30.7 | 17.5 | 17.3 | 7.9 | 26.9 | 36.4 | 21.3 |
| YOLO11m | 35.1 | 20.8 | 20.2 | 10.0 | 31.0 | 41.1 | 67.7 |
| YOLO12s | 29.9 | 17.2 | 16.9 | 7.6 | 26.1 | 35.9 | 19.3 |
| YOLO12m | 34.1 | 19.9 | 19.9 | 9.7 | 30.0 | 43.6 | 60.1 |
| YOLO13s | 29.1 | 16.5 | 16.4 | 7.6 | 25.5 | 35.6 | 20.1 |
| YOLO13l | 34.0 | 19.9 | 19.6 | 9.4 | 30.2 | 41.4 | 84.4 |
| Hyper-YOLOs | 32.0 | 18.3 | 18.1 | 8.4 | 28.0 | 38.7 | 33.8 |
| Hyper-YOLOm | 33.4 | 19.7 | 19.3 | 9.5 | 29.5 | 39.2 | 91.8 |
| RT-DETR-r18 | 36.5 | 20.9 | 20.9 | 11.6 | 30.6 | 37.6 | 58.3 |
| RT-DETR-r34 | 37.0 | 20.9 | 31.2 | 11.6 | 30.7 | 37.9 | 90.6 |
| RT-DETRv2-r18 | 36.6 | 20.9 | 20.9 | 12.2 | 29.8 | 42.0 | 59.9 |
| RT-DETRv2-r34 | 36.2 | 20.8 | 20.7 | 11.8 | 30.0 | 39.3 | 91.9 |
| D-FINE-s | 35.6 | 20.6 | 20.8 | 11.5 | 29.6 | 41.1 | 24.9 |
| D-FINE-m | 36.2 | 20.7 | 20.7 | 11.7 | 30.0 | 41.4 | 56.4 |
| Deim-DFINE-s | 34.0 | 19.7 | 19.5 | 11.4 | 27.6 | 37.9 | 24.9 |
| Deim-DFINE-m | 34.3 | 19.9 | 19.8 | 11.7 | 28.8 | 39.5 | 56.4 |
| **RA-DETR** | **41.0** | **23.7** | **23.9** | **14.5** | **33.6** | **41.5** | **38.6** |

## Environment Installation
conda create -n ra_detr python=3.11
conda activate ra_detr
pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
cd compile_module/mamba
chmod +x make.sh
./make.sh

## Dependencies
Python >= 3.10
PyTorch >= 1.10
## Running Commands

### Training
python train.py -c /home/hulijun/DEIM/configs/yaml/dfine_hgnetv2_s_mg.yml --seed=0
### Evaluation
python train.py -c /home/hulijun/DEIM/configs/yaml/dfine_hgnetv2_s_mg.yml --test-only -r /home/hulijun/DEIM/output
