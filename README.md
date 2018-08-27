# a-method-library-written-by-native-js
一个原生js写的方法库

# 目录结构
	- DOM节点属性和方法简介
	- 实现的DOM方法

# DOM节点属性和方法简介

	1、DOM(文档对象模型):提供了JS操作页面当中元素和节点的属性和方法

	2、获取页面中元素的方法
		document.getElementById();	//获取带有指定 id 的节点（元素）
		document.getElelmentsByTagName(); //返回包含带有指定标签名称的所有元素的节点列表（集合/节点数组）。
		document.getElelmentsByClassName();	//在IE6-8下不兼容.	返回包含带有指定类名的所有元素的节点列表。 
		document.getElelmentsByName();	//在IE中只对表单元素的name起作用
		(document/context).querySelector/querySelectorAll;	//可以以css选择器的形式选择元素，非映射关系，是静态的
		document/context.querySelector/querySelectorAll();	//获取的元素不具有HTML映射关系。是静态的
		
	3、描述节点与节点之间的关系属性
		childNodes;	//获取当前节点下的所有子节点
		children;	//获取元素子节点，在IE6-8下不兼容
		parentNode;	//父亲节点
		document.body;	//获取body标签
		document.docuemntElement;	//获取html文档
		document;	//获取整个document文档
		previousSibling/previousElementSibling;	//获取上一个哥哥节点/上一个哥哥元素节点
		nextSibling/nextElementSibling;	//获取下一个弟弟节点/下一个弟弟元素节点
		lastChild/lastElementChild;	//最后一个节点/最后一个元素节点
		firstChild/firstElementChild;	//第一个节点/第一个元素节点
		element.innerHTML;	//innerHTML属性对于获取或替换HTML元素的内容很有用
		
	4、HTML中最常用的节点及其属性
					nodeType	nodeName		nodeValue
		- 元素结点	1			大写的标签名	null
		- 文本节点	3			#text			文本内容
		- 注释节点	8			#comment		注释内容
		- document	9			#document		null
		
	5、DOM的增删改查
		document.createElement();	//创建一个元素节点
		document.createDocumentFragment();	//创建一个文档碎片元素节点
		parent.appendChild();	//向父元素的末尾追加一个节点
		parentNode.insertBefore(newElement,childNode);	//在父元素的子节点childNode前插入节点newelement
		clone(true/false);	//true表示克隆当前元素和元素内的所有内容。false表示只克隆当前元素
		parentNode.replaceChild(new,child);	//用new节点替换子节点child
		parentNode.removeChild();	//从父元素中删除子元素
		element.getAttribute/setAttribute/removeAttribute();	//获取、设置、删除元素的属性
		
# 实现的DOM方法
	listToArray : 将一个类数组或数组转换成数组的格式
	children : 获取当前元素(curEle)下所有的元素子节点(兼容所有浏览器)
	prev : 获取当前元素(curEle)上一个哥哥元素节点
	next : 获取当前元素(curEle)下一个弟弟元素节点
	prevAll : 获取当前元素(curEle)所有的哥哥元素节点
	nextAll : 获取当前元素(curEle)所有的弟弟节点
	sibling : 获取当前元素(curEle)相邻的两个元素节点,返回一个数组，第一位表示前一个元素节点，第二位表示后一个元素节点。若不存在则显示null
	siblings : 获取当前元素(curEle)所有的兄弟元素节点,返回一个数组
	index : 当前元素(curEle)在同级元素中的索引是多少	
	firstChild : 获取当前元素(curEle)的第一个元素子节点
	lastChild : 获取当前元素(curEle)最后一个元素子节点
	append : 向指定父级元素(parentNode)的末尾追加元素子节点(newEle)
	prepend : 向指定父级元素(parentNode)的开头增加元素子节点(newEle)
	insertBefore : 把目标元素(targetElement)追加到源元素(originElement)的前面
	insertAfter : 把目标元素(targetElement)追加到源元素(originElement)的后面
	addClass : 增加当前元素(curEle)的样式类名(className,字符串形式)。可以写多个类名，类名间以空格隔开
	removeClass : 移除当前元素(curEle)的样式类名(className,字符串形式)。可以写多个类名，类名间以空格隔开
	hasClass : hasClass:判断当前元素(curEle)的是否存在样式类名(className,字符串形式)。
	getElementsByClassName : 获得指定上下文context中含有类名为className的所有元素标签
	getCss : 获取当前元素(curEle)的特定CSS样式(attr)
	setCss : 给当前元素(curEle)的某个样式(attr)的属性值(value).(增加在行内样式上)
	setGroupCss : 批量的设置当前元素(curEle)的样式值(option为一个样式对象)
	css : 获取 单独设置 批量设置当前元素(curEle)的样式值
	win : 获取和设置浏览器窗口本身属性的方法
	offset : 获取页面中任意一个元素(curEle)距离body的偏移量。函数的返回值是一个对象{left:totalLeft , top:totalTop};
		
