# Linux-configure-error-C-compiler-cannot-create-executables
configure: error: C compiler cannot create executables
#编译安装软件报上面的错误
#阅读config.log文件，检查出错原因。发现缺少libmpc.so等等等库，原因是没有配置环境变量
#解决办法：加上gmp、mpfr、mpc的lib库。
export LD_LIBRARY_PATH = /.../.../gmp/lib:/.../.../mpfr/lib:/.../.../mpc/lib:$LD_LIBRARY_PATH
source ~/.bashrc
#然后重新编译安装软件，正常编译
