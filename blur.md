shell 使用`$?`来记录上一条指令的退出码

```bash
FIRST_IP="192.168.1.179"
ping -c1 -t5 $FIRST_IP
if [ $? == 0 ]
then
    ssh yons@"$FIRST_IP"
else
    ssh yons@202.120.36.187 -p 12369
fi
```

原来vscode全局搜索快捷键ctrl+shift+f失灵是由于跟拼音输入法的快捷键相冲突，当初却想当然以为是windows系统的原因。


直接在py里键入"~/xxx/yyy"到普通字符串里是无法被正常识别为home下的路径的，应该使用`os.path.expanduser("~/xxx/yyy")`。


阮一峰的[开发者手册](https://www.ruanyifeng.com/blog/developer/)里有很多实用的教程，遇到小问题时可以去查询，比如今天在上面看到的"最简单的git服务器"，短小精悍，相比csdn的各种教程，清晰且易懂。


TMD，原来git --bare 产生一个不需要工作目录的仓库的意思是仅有git保存数据的部门，也就是说只能进行备份而不能直接对项目进行编辑！


解决pip不与conda环境一致改变的问题：
思路：每当conda activate xxx时，会改变环境变量`CONDA_PREFIX`，由此想到将PATH相应修改以包含相对于当前环境的pip

最初想的是将`export PATH=$CONDA_PREFIX/bin/:$PATH` 加入~/.bashrc，但不能奏效，由于bashrc是在终端开启时仅加载一次，无法实现conda activate动态改变
后通过修改conda可执行文件（实际是一个py脚本）添加`os.environ['PATH'] = f"{os.getenv('CONDA_PREFIX')}/bin/:{os.getenv('PATH')}"`达到动态更改的效果

在构建shielded env时用到了工厂模式，避免过深的参数传递，以及隐藏了构建对象过程的复杂细节（如使用共享game）