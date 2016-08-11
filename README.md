alogic-xscript-zk
=================

alogic-xscript-zk是基于xscript2.0的zookeeper插件，提供了使用zk所需的相关指令，无缝对接zookeeper。

### 案例

下面的案例是对本地ZooKeeper的基本操作。

	<?xml version="1.0"?>
	<script>
		<using xmlTag = "zk-conn" module = "com.alogic.xscript.zk.ZKConn" />
		
		<!-- 创建一个连接到本地ZooKeeper -->
		<zk-conn connectString = "127.0.0.1:2181">
	
			<!-- 获得路径 / 下的子节点信息 -->
			<zk-children path = "/" tag = "data"/>
		
			<!-- 获得/APP1/节点数据 -->
			<zk-get path = "/APP1" id = "app1data"/> 
		
			<!-- 查看/APP2/节点是否存在 -->
			<zk-exist path = "/APP2/" />
			
			<!-- 创建/APP2/节点 -->
			<zk-mkpath path = "/APP2/" mode = "0" />
			
			<!-- 查看/APP2/节点是否存在 -->
			<zk-exist path = "/APP2/"/>
			
			<!-- 给/APP2/节点设置数据 -->
			<zk-set path = "/APP2/" mode = "0" data = "this-is-app2-data" />
			
			<!-- 查看/APP2/节点数据 -->
			<zk-get path = "/APP2/" id = "app2data" />
				
			<!-- 删除/APP2/节点 -->
			<zk-delete path = "/APP2/" />
			
			<!-- 查看/APP2/节点是否存在 -->
			<zk-exist path = "/APP2/" />
		
		</zk-conn>
	
	</script>


### 如何开始？

为正确执行上述指令，需要在本地安装好ZooKeeper并启动。

ZooKeeper启动后，就可以运行[demo](src/test/java/Demo.java)来测试xscript脚本。

### 指令参考

参见[alogic-xscript-zk参考](src/docs/reference.md)。

### 版本历史
    
- 3.4.6 [20160809 duanyy]
	+ 初次发布
- 3.4.6 [20160811 lijun]
	+ 补充了包com.alogic.xscript.zk内的ZooKeeper基本操作，并完成相关文档编写
