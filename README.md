应用场景：

找到了可以劫持dll的白程序，接下来需要制作黑dll
本工具可以自动提取dll的导出函数，并生成pch.cpp文件

pch.cpp文件用于黑dll制作，可以直接编译。

辅助红队，寻找白程序调用dll的导出函数的顺序

根据messagebox弹窗，可以找到该程序调用的第一个函数，我们就在里面加上shellcode

如此一来，白程序被劫持到我们制作的黑dll时，就会第一时间执行我们的shellcode

这样是导出函数来执行shellcode，不是在dllmain里面执行

避免了死锁的问题
