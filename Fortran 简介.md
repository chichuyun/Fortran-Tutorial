Fortran是Formula Translation的缩写，是历史上第一种高级计算机语言，它是上世纪50年代由IBM公司设计并研发用于科学计算的语言。Fortran一直以高性能著称，有强大的数组操作功能。Fortran77版本的发布，使得Fortran在业内流行起来。但后续版本的严重滞后，使得近来Fortran变得不流行。现在大多也只是在科研领域会见到Fortran的身影。

Fortran90/95标准中加入了现代语言的风格，例如引入了自由编程格式。Fortran03/08标准更是引入了面向对象的功能，后续版本中也引入了并行实现(Coarray)，之前的版本Fortran是不支持并行功能的，因此衍生出了一些支持并行功能的Fortran分支，例如openmp和openmpi。最新的Fortran18标准中还引入了函数式编程的范式。

Fortran是一种静态语言，从而需要编译后才能执行，现在比较流行的编译器有intel开发的ivf编译器以及开源组织GNU的gfortran编译器，不同的编译器含有不同于标准的功能，这里才用gfortran编译器并在64位的windows系统上进行演示。最新的gfortran版本是8.3.0，官方网址：

https://gcc.gnu.org/wiki/GFortran/

编辑器我推荐使用Code::Blocks，编辑器内部自带某一版本的gfortran，下载地址：

http://www.codeblocks.org/



编译器也可在MSYS2或Cygwin中进行下载安装，这样可以随时更新编译器版本。这里采用MSYS2。下载地址：

https://sourceforge.net/projects/msys2/



MSYS2提供了Arch Linux上强大的包管理器pacman。

安装完后打开终端输入如下命令：

> pacman --needed -Sy bash pacman pacman-mirrors msys2-runtime

> pacman -S  base-devel  git  mercurial  cvs  wget  p7zip  perl  ruby

> pacman -S --force mingw-w64-x86_64-toolchain

> pacman -S mingw64/mingw-w64-x86_64-gcc

> pacman -S mingw64/mingw-w64-x86_64-gcc-libgfortran

安装过程中可能在某一个地方卡很久，这里不要着急关闭终端，耐心多等一会。

之后可用命令pacman -Syu进行更新升级。

然后将安装目录下的\msys64\mingw64\bin和\msys64\usr\bin挂载到系统环境变量(PATH)中去。

接着修改Code::Blocks中的编译器设置(Settings/Compiler)。将位置的文件都改为\msys64\mingw64\bin目录下的。


自此Fortran的环境搭建完成。

点击File，创建一个Project(仅仅新建一个source文件容易出现自动补全功能缺失的问题，另外也不建议这样做)，默认会有一个Hello World!代码，点击编译运行，屏幕中就会出现Hello World!的输出。

