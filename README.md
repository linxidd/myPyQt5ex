#PyQt5/Python2.7 学习心得
###1、地址簿分析
`QGridLayout`,`Qt`         /example/tutorials/addressbook/


**1.1** 建立无parent类`AddressBook`，继承`Qwidget`类，注意`super`的用法，初始化`QWidget`的静态变量，所以AddressBook成为置顶窗口。
在使用`QWidget`中组件时应注意，对于每个实例相同的变量直接定义为变量名，如需不同实例不同显示的定义为`self.variable`。
`QWidget`->`QGridLayout`为界面网格布局，参数一为已创建的部件名称，第二第三为部件位置，参数四为可选参数表示布局位置，`Qt`类为界面布局提供了对齐方式。最后将网格布局传递给实例的`setLayout`函数，并设置窗口标题。

对于所有`QWidget`基础的GUI程序必须使用`QApplication`，对于其他情况使用`QGuiApplication`，然后创建AddressBook实例，并使用show函数显示。

**1.2**首先分析窗口部件，创建了输入栏和输入框，并且`setReadOnly`为True，使其成为只读状态。又构建了三个按钮，并通过`QWidget`的函数设置Add按钮为`show()`，其他按钮隐藏。这里需要注意按钮名称的设置，通过名称前的&字符表明该按钮可以使用Alt+&后收个字母的形式触发也就是快捷键。
其后将按钮点击信号和slot函数连接，从而在点击该按钮后执行slot函数表示的事件。窗口布局同时使用了`QVBoxLayout`和`QGridLayout`。然后将`QGridLayout`传递给窗口的`setLayout`函数。
点击Add按钮后，事件传递给`addContact`函数，函数获取文本行和文本框的文字，并清空，同时设置可编辑属性并将光标初始化到文本行，通过`setEnabled`函数将Add按钮置为无效，并显示summit、cancel按钮。
点击summit按钮后，传递文本行和文本框的文字。如果都为空，显示提示框。

**1.3**该GUI比1.2增加previous和next按钮，可以浏览已经录入的地址信息。