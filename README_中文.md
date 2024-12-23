# Nd-Mamba2 for any dimension by pytorch
仅使用PyTorch实现的双向Mamba2（BiMamba2）提供N维度支持，包括1d，2d，3d数据的支持，借助BiMamba2你可以很方便的缝合到任意模型中去提高精度。

下面的文章详细介绍了该项目的Nd-Bimamba2模块：
> **Nd-BiMamba2: A Unified Bidirectional Architecture for Multi-Dimensional Data Processing**\
> Hao Liu*\
> Paper: [https://arxiv.org/abs/2312.00752](https://arxiv.org/abs/2411.15380)
 
[![DOI](https://zenodo.org/badge/837076504.svg)](https://doi.org/10.48550/arXiv.2411.15380)
[![DOI](https://zenodo.org/badge/837076504.svg)](https://doi.org/10.5281/zenodo.14185321) 
 
![结构](img.png)

## [nd_mamba2.py](torchnssd/nd_mamba2.py)特点（更新时间：2024/08/02）
- ✅ 支持定制的1d数据(batch,channel,length)
- ✅ 支持定制的2d数据(batch,channel,height,width)
- ✅ 支持定制的3d数据(batch,channel,deep,height,width)
- ✅ 支持通用的Nd数据(batch,channel,*size)
- ✅ 有好的环境支持（纯PyTorch实现，即插即用）
  
## [ex_bi_mamba2.py](torchnssd/ex_bi_mamba2.py)新特性（更新时间：2024/08/16）
- ✅ 支持torch.jit.scipt格式导出（取消了einops库以及配置类）
- ✅ 支持onnx格式导出（采用onnx_14的版本，支持下三角阵的操作）
- ✅ 更易阅读 (删除了大量冗余代码) 
- ✅ 兼容nd_mamba2.py的所有特点
  
## [ex_bi_mamba2_ac.py](torchnssd/ex_bi_mamba2_ac.py)新特性（更新时间：2024/08/20）
- ✅ 更好的2d图像语义表达（使用非对称卷积的策略优化2d）
- ✅ 兼容ex_bi_mamba2.py中的所有特点
- ❌ 不支持1d、3d等其他维度的数据格式

## [vssd_torch.py](torchnssd/vssd_torch.py)新特性（更新时间：2024/08/21）
- ✅ 更好的2d图像语义表达（基于[VSSD]( https://github.com/YuHengsss/VSSD  )的优化）
- ✅ 友好的环境支持（纯torch实现，即插即用）
- ❌ 不支持导出为scipt及onnx格式
- ❌ 不支持1d、3d等其他维度的数据格式

## [ex_vssd.py](torchnssd/ex_vssd.py)新特性（更新时间：2024/08/22） 
- ✅ 更易阅读 (对vssd_torch进行了代码优化) 
- ✅ 支持导出为scipt及onnx格式
- ✅ 兼容ex_vssd.py中的所有特点
- ❌ 不支持1d、3d等其他维度的数据格式

## [ex_vssd_cls_seg.py](torchnssd/ex_vssd_cls_seg.py)新特性（更新时间：2024/08/28） 
- ✅ 支持分割任务（添加了基于vssd backbone的shuffle分割解码器）
- ✅ 支持分类任务（添加了基于vssd backbone的shuffle分类解码器）
- ✅ 支持导出为scipt及onnx格式 
- ❌ 不支持1d、3d等其他维度的数据格式

## 提示
*如果你想要更快的速度，可以将本项目中的Mamba2替换为Mamba2官方的Cuda加速实现，并按照官方要求安装各种依赖包，这不会影响本项目对多维度数据的支持，但会对模型的导出产生影响*
 
   
## 致谢 
* [Albert Gu], [Tri Dao] [state-spaces/mamba](https://github.com/state-spaces/mamba) - authors of the Mamba-2 architecture
* [Yuheng Shi], [Minjing Dong] [YuHengsss/VSSD](https://github.com/YuHengsss/VSSD) - authors of the vssd architecture
* [Thomas] - author of [tommyip/mamba2-minimal](https://github.com/tommyip/mamba2-minimal), who inspired this repo


  

## 引用
```
@misc{liu2024ndbimamba2unifiedbidirectionalarchitecture,
      title={Nd-BiMamba2: A Unified Bidirectional Architecture for Multi-Dimensional Data Processing}, 
      author={Hao Liu},
      year={2024},
      eprint={2411.15380},
      archivePrefix={arXiv},
      primaryClass={cs.LG},
      url={https://arxiv.org/abs/2411.15380}, 
}
```

