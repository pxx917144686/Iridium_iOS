# Iridium

使用 fouldecrypt 完全静态。支持 iOS 13.5 <-> 14.4.1
![Preview](./Workflow/Preview/main.png)



一、旧版本DumpDecrypter——>是基于dumpdecrypted的优化版本。
      
       DumpDecrypted~ 是经典的开源的  动态脱壳!  ——> 只解密APP的可执行文件——>重点——>不是全权限的包


二、frida-ios-dump——>重点——>基于 Frida 框架——>动态解密!——>但是 是“接近  全权限脱壳工具”(区别于——>DumpDecrypted只解密APP的可执行文件. 不完整,比如缺失小组件扩展;)


三、Bagbak
       首先就是需要基于 macOS,去执行命令行操作——>从越狱设备上——>提取目标APP的所有文件，配置文件、数据库、图片~~~ Bagbak 能够导出APP的所有资源文件，而不仅仅是”可执行文件”获取APP~~~  的完整文件系统结构，不仅仅是解密应用的可执行文件。


四、Bagbak是基于开发者NyaMisty在脱壳工具在 flexdecrypt2 的基础上[开发者NyaMisty 的分析，在 iOS 14 之后 dyld 本身不再在用户态调用 mremap_encrypted 解密] 非常依赖于“frida”~ frida-ios-dump(基于 Frida 框架)

        我实际测试是:在iOS14.4.1之后失效~就是接近静态脱壳的工具“Iridium”在iOS14.4.1以上失效了~
        开发者NyaMisty又研究出了flexdecrypt2~
        Bagbak开发者看见了flexdecrypt2 在技术实现上借鉴或融合flexdecrypt2 的特性~


五、“最新版本的 DumpDecrypter”  就是“狗哥”那个——>在技术实现上~应该、可能、也许——>借鉴或融合Bagbak的特性~


关于、静态脱壳工具：Iridium——>fouldecrypt 完全静态(就是不需要APP运行能够绕过越狱检测。通过模拟 dyld 使用 mremap_encrypted 进行脱壳)实际测试中——>支持 iOS 13.5 <-> 14.4.1
