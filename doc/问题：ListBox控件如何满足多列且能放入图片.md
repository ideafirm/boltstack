BOLT的核心思想在于元对象和元对象的自由组合， 可以实现功能丰富的各种组件，像你说的这种listbox都是可以很容易的实现。

首先要对你的listbox进行结构分析，典型的来说listbox当中每一行都可以作为一个子单元，这个层面可以定义一个行控件，每行又可以再拆分，拆成几列，每列又对应一个单元格，单元格内容非常自由了，可以是任意的元对象，也可以再有一层控件封装，所以这层放图片和放文本没有什么差别，哪怕放一个edit、flash都一样。

一定要和win32传统的listbox分开，传统listbox里面放个图片可能很困难，需要做很多事情，但在bolt里面，这都是自然而然的基础支持，ImageObject，TextObject这些元对象就是组合更复杂控件的基石，只要你能把你要做的东西结构合适的分层，分块。

至于动态多一行，多一列，这些东西都是可以在脚本里面动态操控的，不是xml配置的就是固定的。这和在win32里面也是一样的，传统的listbox也是要动态添加数据的。