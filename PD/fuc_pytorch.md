## 函数
- os.getcwd()：返回当前工作目录
- result = np.array(image) 
  -效果：result.shape=[width,height,channels]
- ZipFile模块：zip格式编码的压缩和解压缩
  - ZipFile和ZipInfo两个类
    - ZipFile：主要的类，用来创建和读取zip文件
    - ZipInfo：存储的zip文件的每个文件的信息
      - f = zipfile.ZipFile('test.zip')  # 读取文件
      - f.extractall('channel')  # 将所有文件解压到channel目录下
