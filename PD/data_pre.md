### NIFTI格式图像
- Analyze
  - Analyze格式：每组数据包含2个文件，一个为数据文件（img），包含二进制的图像资料；另一个为头文件（hdr），包含图像的元数据
  - High-Dynamic Range（HDR），Analyze格式的主要不足就是头文件（hdr）不能真正反映元数据
  - 软件：Mricron
- NIFTI
  - NIFTI格式是“换装”后的Analyze 7.5格式。ANALYZE 7.5 中的header文件（扩展名为.hdr）用于存储meta-information，而实际数据以扩展名为.img 存储，故NIFTI格式存储的数据使用了一对文件 .hdr/.img , 扩展名为.nii
  - NIFTI 的header ：一共有348 bytes（字节），存放不同作用的field(字段)
  - 标准NIFTI图像的扩展名是.nii，也包含了头文件和图像资料，单独的.nii格式文件的优势就是可以使用标准的压缩软件（如gzip）进行压缩
  - 一些分析软件包（如FSL）可以直接读取和写入压缩的.nii文件（扩展名为.nii.gz）
  - 软件：ITK-SNAP，三个角度的视图：水平面、矢状面、冠状面



### 将Analyze(.hdr)转换成.nii,再将.nii转换成jpg或者png
- .nii和.nii.gz格式是一样的

## 待解决的问题
- 1.nii文件或者hdr文件的标注格式是怎么样的，分类模型输入图像格式能否识别？
- 2.ITK和MriCron软件是如何打标注的
- 3.nii文件转jpg是怎么获取的，是按照什么区间进行导出jpg图像
- 4.现有的脑部图像有没有相关的分类模型，分割模型也可以考虑
- 总结：需要根据数据进行分析判断，是先做分类还是分割
  
- 迁移学习：将脑部分割或分类模型的预训练权重直接迁移至目标领域，也就是纹状体帕金森病的分割或者分类。
- 所以找到预训练模型权重是下一步需要做的调研工作 

— label格式也是nii，是不是接下来就是将nii格式转换成png，然后通过unet去做分割？分类怎么做？nii怎么转换成mask格式？

- 试着label2jpg看看mask的格式，能不能用模型来做分类？
- U-Net系列几乎label是png格式
