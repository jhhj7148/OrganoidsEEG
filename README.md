关于这个部分首先我想要实现脑类器官的睡眠预测
通过类器官EEG（oEEG）的手段来预测脑类器官是否会睡觉
然后接下来是去通过oEEG的方式去观测其是否存在睡眠稳态以及睡眠补偿相关的一个分类
然后探索昼夜节律（Process C）和睡眠稳态（Process S）（睡眠压力）之间的联系

项目简介
========
该仓库包含了一套用于脑类器官(Organoid)多电极阵列(\*MEA\*)记录和分析的脚本及示例笔记。本项目旨在通过类器官EEG(oEEG)数据研究睡眠样活动、睡眠稳态以及昼夜节律等生理现象。

目录结构
--------
- `Axion/`：用于读取和处理Axion原始数据的MATLAB函数，其中包含官方指南 `AxionBioSystems_Matlab_guide.pdf`。
- `functions/`：常用的预处理和特征计算脚本，如 `MEA_convert.m`、`compute_nEEGfeats.m` 等。
- `util_funcs/`：信号处理和突触事件检测等辅助函数。
- `scripts/`：若干分析流程示例脚本，需根据个人数据路径进行修改。
- `methods/`：存放项目相关的文献资料，分为 `dry_lab` 与 `wet_lab` 两类，方便日后补充PDF等文件。
- `*.ipynb`：基于Python的Jupyter Notebook，用于进一步的数据探索和模型建立。

依赖环境
--------
1. **MATLAB** (建议 R2018a 及以上版本) 及其 Signal Processing Toolbox。
2. **Python 3** 环境，推荐安装 `numpy`、`scipy`、`pandas`、`matplotlib`、`seaborn` 等库，用于运行笔记本中的分析代码。

快速开始
--------
1. 准备好由Axion设备采集的 `.raw` 或 `.spk` 数据文件。
2. 使用 `functions/MEA_convert.m` 将原始数据解包并保存为MATLAB可读格式。
3. 根据需要编辑 `scripts/` 目录下的脚本(例如 `corticoid_script.m`) ，修改其中的数据路径并运行以计算网络尖峰、LFP及其他特征。
4. 可在 Jupyter Notebook 中加载生成的 `.mat` 文件，执行 `organoid_EEG_age_regression.ipynb` 等笔记本进行进一步分析或绘图。

注意事项
------
仓库中的示例脚本普遍含有绝对路径(如 `/Users/rdgao/...`)，在实际使用前请全部替换为自身的文件存储路径。数据文件未包含在仓库中，需要自行准备或联系作者获取。

