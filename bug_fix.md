#Light tracks bugs, use the dark theme
ir_env模块生成空白gif的问题：由于其他模块调用了plt.subplots()，因此ir_env模块使用plt.savefig会有问题，改为self.fig.savefig

vscode 的setting sync报错了 “LocalInvalidContent (UserDataSyncError) syncResource:settings operationId:unknown: Unable to sync settings as there are errors/warning in settings file.”  暂时不知道怎么解决

解决使用moviepy创建TextClip时报错
```
OSError: MoviePy Error: creation of None failed because of the following error:

convert: not authorized `@/tmp/tmp__gwjasj.txt' @ error/property.c/InterpretImageProperties/3518.
convert: no images defined `PNG32:/tmp/tmp5ie4nz8y.png' @ error/convert.c/ConvertImageCommand/3258.
```
[问题链接](https://askubuntu.com/questions/873112/imagemagick-cannot-be-detected-by-moviepy)