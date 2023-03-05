#####批量复制某文件到多个文件夹
```
ls ./ | grep taxi | xargs -n 1 cp -v ./taxi/get_parameter.sh 
```
cp: './taxi/get_parameter.sh' 与'taxi/get_parameter.sh' 为同一文件
'./taxi/get_parameter.sh' -> 'taxi11/get_parameter.sh'
'./taxi/get_parameter.sh' -> 'taxi22/get_parameter.sh'
'./taxi/get_parameter.sh' -> 'taxi33/get_parameter.sh'
'./taxi/get_parameter.sh' -> 'taxi44/get_parameter.sh'
'./taxi/get_parameter.sh' -> 'taxi55/get_parameter.sh'