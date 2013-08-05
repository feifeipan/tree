tree
====

A tree build of doms and canvas


来源
====
显示程序之间调用关系，例如A接口调用了B接口，B接口继而又调用了C1和C2两个接口....（url lantency)

为了将复杂的关系图形化显示出来。尝试了开源的几个tree, 因为这个接口调用会有错综复杂的情况。比如C1又会再次调用B。所以一般的tree结构无法表达。

准确的说，她并不是一般的tree，而是有一个更好听的名字“A force directed graph“


构思
===

因为数据会有几个根节点，所以会展示N棵树。页面会首先横向分割成N行。
在每一个棵树中，再根据children的个数m，纵向分割成m列。
每一个节点有自己的parent和children属性，由一个dom元素显示。
节点之间的关系由canvas来划线。如果在不同的水平线/纵向线上，那么就直接将两个节点中点链接起来；如果在同一个水平线上，那么需要花一个类似 |_| 这种图形。

数据格式
===
var data = [
  	"appid1-RTb@appid2-RTe@appid3-RTd@appid5-RTf@appid11-RTqappid11-RTqappid11-RTq",
  	
		"appid1-RTb@appid2.1-RTc@appid4-RTd@appid5-RTg@appid7-RTi@appid11-RTq",
		"appid1-RTb@appid2.1-RTc@appid5-RTg@appid6-RTh@appid11-RTq",
		"appid1-RTb@appid2.1-RTc@appid5-RTg@appid7-RTi",
		"appid1-RTb@appid3-RTc@appid8-RTm@appid9-RTn@appid10-RTk@appid13-RTq",
		"appid21-RTb1@appid22-RTe@appid31-RTd@appid51-RTf@appid111-RTq"
	];


