#PyQt5/Python2.7 学习心得
###1、地址簿分析
`QGridLayout`,`Qt`         /example/tutorials/addressbook/
1.1建立无parent类`AddressBook`，继承`Qwidget`类，注意`super`的用法，初始化`QWidget`的静态变量，所以AddressBook成为置顶窗口。
在使用`QWidget`中组件时应注意，对于每个实例相同的变量直接定义为变量名，如需不同实例不同显示的定义为`self.variable`。