# Maven
Maven相关

1. idea springboot maven 打包记录

> 多模块引用的时候，模块之间有引用，common模块应该是一个不可启动的模块，提供公共的服务，在common的build plugins 中不能加上 打包插件，
参考：https://blog.csdn.net/y_hai_yang/article/details/81004451 
这个坑太大了，踩了很久 终于看到了这篇文章，才解决，不能在引用的common中加上spring-boot-maven-plugin插件，因为这个SpringBoot插件会在Maven的package后进行二次打包，目的为了生成可执行jar包，如果C中定义了这个插件，会报错提示没有找到main函数。
