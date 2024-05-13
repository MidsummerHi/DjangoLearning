<center><h3>Datawhale组队学习-Django学习-task1学习输出</h3></center>

### 一、杂七杂八的规范

要做好一个项目，我们必须规范自己的开发行为，以下几点是正式开始前的一些习惯：

- 正式开发前，请为自己的工程创建一个工程目录，然后所有的工作在工程目录下完成
- 控制台的目录应该调整为工程目录
- 运行任何命令之前请确保自己处于正确的虚拟环境当中

请记住，以上并不是

### 二、 环境配置(以windows为例)

1. ##### 虚拟环境安装与激活

   首先运行如下命令，创建一个虚拟环境

   ```cmd
   conda create -n Name_VirEnv python=3.11 -y
   ```

   以上命令中，参数`Name_VirEnv`需更改为你自己喜欢命名，比如我的的环境名字就叫`erp_venv`；此外参数`python=3.11`是指定python的版本，读者可自行指定。⚠️建议版本不要太低，以免引起依赖包的安装失败。

   接着运行如下命令完成环境激活

   ```cmd
   conda activate Name_virEnv
   ```

2. ##### 依赖包安装

   - ##### 方法1

   Django目前所需要的所有依赖包，列出如下，可将其拷贝，直接复制到控制台中回车运行，即可完成安装（如果网络正确）

   ```cmd
   pip install django
   pip install djangorestframework
   pip install django-filter
   pip install drf_spectacular
   pip install django-debug-toolbar
   pip install django_extensions
   ```

   - ##### 方法2

   还有一种做法，将包名写到一个`txt`文件中，如下所示为该文件的内容:

   ```
   django 
   djangorestframework 
   django-filter 
   drf_spectacular 
   django-debug-toolbar 
   django_extensions
   ```

   并为其命名为`requirements.txt`，然后保存到控制台当前运行的目录下；接着运行如下命令，完成包的安装：

   ```cmd
   pip install -r requirements.txt
   ```

   目前对于我们这个小程序来说，看来比较麻烦，但对于依赖很多的程序来说，是一个很好的解决方案。

3. 