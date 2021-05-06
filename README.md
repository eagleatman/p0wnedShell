# p0wnedShell
使用https://github.com/Cn33liz/p0wnedShell
项目在win7(64)使用Visual Studio2013生成的release x64的可执行文件，未做任何改动
生成日期是2021.5.6
# 注意
如果你想自己生成也是可以的，这里在安装visual studio2013的时候会有一个ie10为安装的保存，解决方法如下：
+ 在本机系统上建立一个文件--1.bat，内容如下:
~~~shell
@ECHO OFF
 
:IE10HACK 
REG ADD "HKLM\SOFTWARE\Wow6432Node\Microsoft\Internet Explorer" /v Version /t REG_SZ /d "9.10.9200.16384"/f 
REG ADD "HKLM\SOFTWARE\Wow6432Node\Microsoft\Internet Explorer" /v svcVersion /t REG_SZ /d "10.0.9200.16384"/f 
REG ADD "HKLM\SOFTWARE\Microsoft\Internet Explorer" /v Version /t REG_SZ /d "9.10.9200.16384" /f 
REG ADD "HKLM\SOFTWARE\Microsoft\Internet Explorer" /v svcVersion /t REG_SZ /d "10.0.9200.16384" /f 
GOTO EXIT
 
:REVERTIE 
REG DELETE "HKLM\SOFTWARE\Wow6432Node\Microsoft\Internet Explorer" /v svcVersion 
REG DELETE "HKLM\SOFTWARE\Microsoft\Internet Explorer" /v svcVersion 
REG ADD "HKLM\SOFTWARE\Wow6432Node\Microsoft\Internet Explorer" /v Version /t REG_SZ /d "8.0.7601.17514" /f 
REG ADD "HKLM\SOFTWARE\Microsoft\Internet Explorer" /v Version /t REG_SZ /d "8.0.7601.17514" /f 
GOTO EXIT
 
:EXIT
~~~
+ 右键使用管理员运行，就会骗过vs的检查器限制
