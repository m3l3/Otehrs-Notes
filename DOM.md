### 1. DOM 概念

DOM : Document Object Model，文档对象模型。

当浏览器加载了一个网页后，DOM 根据网页文档创建了一文档对象。

对象是一种独立的数据集合，与对象相关联的变量称为对象的属性，通过对象调用的函数成为对象的方法。

DOM 代表着被加载到浏览器窗口里的当前网页。DOM 把一份文档表示为一棵树。

#### 节点

文档是由节点构成的集合，此时的节点代表文档树上的树枝和树叶。有的 DOM 节点还包含其他类型的节点。

1. 元素节点

    DOM 的原子即为 __元素节点__ （element node）。这些元素在文档中的布局形成了文档的结构。各种标签提供了元素的名字。元素可以包含其他元素 —— 唯一不会被其他元素包围的元素是 <html> 元素，它是整个节点的根元素

2. 文本节点

   在 XHTML 中，文本节点总是被包含在元素节点的内部，但并非所有的元素节点都包含由文本节点。

3. 属性节点

    属性是对元素的具体描述，属性总是被放在起始标签里，所以属性节点总是被包含在元素节点中。并非所有的元素都包含由属性，但所有的属性都被包含在元素中。

4. CSS

    CSS 并不属于 DOM，CSS 是告诉浏览器应该如何显示一份文档的内容。类似 DOM，CSS 也把文档的内容视为一颗节点树。节点树上的各元素继承其父元素的样式属性。

    为了把一个或几个元素与其他元素区别开来，经常需要使用 class 属性或 id 属性

    - class 属性

    所有的元素都由 class 属性，__不同__的元素可以有__相同__的 class 属性值。

    - id 属性

    id 属性的用途是给网页里的某个元素加上一个独一无二的标识符。每个元素只能由一个 id 属性值，不同的元素必须由不同的 id 属性值。id 属性用于连接文档中的某个元素和 CSS 样式表里的某个样式。

#### getElementById() 方法

这个方法将返回一个与给定 id 属性值的元素节点相对应的对象。这个方法是与 document 相关联的函数。使用时函数名后边必须根由一对圆括号，包含着函数的参数 —— 即所要获得的那个元素的 id 值，这个 id 值必须放在单引号或双引号中。

  `document.getElementById('idValue')`

这个调用会返回对应 id 值的那个 document 对象。由于 id 值是独一无二的，所以返回的对象也是唯一的。

- 文档中的每一个元素都对应着一个对象。利用 DOM 提供的方法，可以把这些元素相对应的任何一个对象筛选出来。

- 一般来说，不需要对文档中的每一个元素都定义一个 id 值，除了使用 id 值外，可以使用其他 DOM 方法来筛选对象。

#### getElementsByTagName() 方法

getElementByTagName() 方法将返回一个对象数组，每个对象分别对应文档中有给定标签的一个元素。类似 getElementById()，这个方法也只有一个参数 —— 标签的名字。

  `document.getElementByTagName(tagValue)`

与 getElementById() 十分类似，但是 getElementByTagName() 方法返回的是一个对象数组。

getElementByTagName() 方法还允许我们把一个通佩符当作它的参数，这样文档中的所有元素都会被返回。


#### getAttribute() 方法

当我们定位到特定元素节点后，可以使用 getAttribute() 方法把它的属性值查询出来。这个方法的参数也是一个 —— 需要查询的属性的名字。

  `object.Attribute(attribute)`

getAttribute() 方法不能通过 document 对象调用，必须通过一个元素节点对象来调用。当需要查询的属性不存时则返回 null。

#### setAttribute() 方法

setAttribute() 方法用于对属性节点的值进行修改。类似于 getAttribute() 方法，必须通过元素节点对象调用的函数，但 setAttribute() 方法需要传递两个参数：

  `object.setAttribute(attribute, value)`

即便要更改的属性并不存在，setAttribute() 也可以首先将属性创建出来，然后对值进行设置。如果属性存在，则直接将原有的值覆盖。

- 通过 setAttribute() 方法对文档做出的修改，将使得文档在浏览器窗口里的显示效果或行为动作发出相应的变化，但查看源代码会发现原来的属性值并没有发生变化。这表明了 DOM 的一个重要特性：先加载文档的静态内容、再以动态的方式对它们进行刷新，动态刷新不影响文档的静态内容。—— 因此 DOM 对页面内容的刷新不需要用户执行刷新操作。








