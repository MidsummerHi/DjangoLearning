<center><h3>Datawhale组队学习-Django学习-task1学习输出</h3></center>

### 一、杂七杂八的规范

要做好一个项目，我们必须规范自己的开发行为，以下几点是正式开始前的一些习惯：

- 正式开发前，请为自己的工程创建一个工程目录，然后所有的工作在工程目录下完成
- 控制台的目录应该调整为工程目录
- 运行任何命令之前请确保自己处于正确的虚拟环境当中

请记住，以上并不是完全要求的，但是为了少给自己惹麻烦，还要多提醒自己做好规范操作。

### 二、 环境配置(以windows为例)

1. ##### 虚拟环境安装与激活

   首先运行如下命令，创建一个虚拟环境

   ```cmd
   conda create -n erp_venv python=3.11 -y
   ```

   以上命令中，参数`erp_venv`需更改为你自己喜欢命名，比如我的的环境名字就叫`erp_venv`；此外参数`python=3.11`是指定python的版本，读者可自行指定。⚠️建议版本不要太低，以免引起依赖包的安装失败。

   接着运行如下命令完成虚拟环境激活

   ```cmd
   conda activate erp_venv
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

### 三、Django程序开发初试

1. ##### 程序工程目录和程序本身的创建

   - ##### 创建程序工程目录

     ```cmd
     django-admin startproject MyFirstProject
     ```

     以上命令，前两个字符串都属于固有命令字符串，该命令用于创建一个程序目录；`MyFirstProject`为要创建的程序工程目录名字，读者可自定义；

     创建完后，应该会生成一个名为MyFirstProject的文件夹，其内容如下目录树所示：

     ```cmd
     │  manage.py
     │
     └─MyFirstProject
             asgi.py
             settings.py
             urls.py
             wsgi.py
             __init__.py
     ```

     上述目录树的生成可在命令行进入对应目录后运行以下命令生成

     ```cmd
     tree /f
     ```

   - ##### 创建程序

     运行下面命令，进入程序工程目录

     ```cmd
     cd MyFirstProject
     ```

     然后用django提供的命令创建一个程序

     ```cmd
     django-admin startapp MyFirstAPP
     ```

     上述命令中，运行完后，将生成一个新的名为`MyFirstAPP`的文件夹，文件夹中包含程序正式开发前必须的一些初始化文件，再次在工程目录中运行`tree /f`将得到如下目录结构。

     ```cmd
     │  manage.py
     │
     ├─MyFirstApp
     │  │  admin.py
     │  │  apps.py
     │  │  models.py
     │  │  tests.py
     │  │  views.py
     │  │  __init__.py
     │  │
     │  └─migrations
     │          __init__.py
     │
     └─MyFirstProject
             asgi.py
             settings.py
             urls.py
             wsgi.py
             __init__.py
     ```

2. ##### 程序运行前参数调整

   1. 更新程序目录下的`apps.py`文件，以我为例

      - 文件原始内容

        ```python
        from django.apps import AppConfig
        
        class MyfirstappConfig(AppConfig):
            default_auto_field = "django.db.models.BigAutoField"
            name = "MyFirstApp"
        
        ```

      - 修改后

        ```cmd
        from django.apps import AppConfig
        
        class MyfirstappConfig(AppConfig):
            default_auto_field = "django.db.models.BigAutoField"
            name = "MyFirstProject.MyFirstApp"  # 修改为"工程名.程序名"的形式
        
        ```

   2. 设置程序目录下`setting.py`文件

      - 

   3. 

3. 启动程序