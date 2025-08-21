
第四章-numpy模块的使用
	1 数组的创建与操作(ndarray)
		创建数组
			np.array(list) 
			np.array(tuple)
		数组元素的返回
			在一维数组中，列表所有的索引方法都可以用。而且还可以将索引组装成列表，获取对应位置的元素。
			在二维数组中，[rows,cols],rows获取行索引，cols获取列索引
				如果要获取所有行或列元素，用英文冒号:代替对应的rows、cols
			
				#ix_ 笛卡尔积
				print(arr[np.ix_([0,-1], [1,3])]) # (0,1) (0,3) (-1,1) (-1,3)
			
		数组的常用属性
			ndim	维度，轴数
			shape	形状，行列数(m,n)
			dtype	元素的数据类型
			size 	元素个数(m*n)
		
		数组的形状处理
			修改数组形状（重塑）
			reshape		改的是副本(参数-1代表一维)
			resize		功能与reshape类似，改的是视图
			ravel		多维转一维,默认按行降维(order='F'按列降维)，改的视图(默认按行降维)
			flatten		与ravel类似,改的是副本
		
		数组的堆叠
			row_stack：用于垂直方向（纵向）的数组堆叠，列数必须相同
			column_stack：用于水平方向（横向）的数组合并，行数必须相同
			vstack：其功能与row_stack函数一致
			hstack：其功能与colum_stack函数一致
			
		
	2 数组的基本运算方法
		数学运算符
			+ - / *  % // **
		比较运算符
			> >= < <= == !=
			可以用来从数组中查询满足条件的元素，
			或者根据判断的结果执行不同的操作。
			
	3 常用数学和统计函数
		np.sum(arr,axis)	按照轴的方向计算和，axis=0表示按垂直方向计算，axis=1表示水平方向计算数组的和
		
	4 线性代数的求解
		常用的线代函数（了解）
		np.zeros
		np.ones	
		np.dot(arr1,arr2) 点积，第一个数组的列数必须等于第二个数组的行数
		np.diag(arr)	取出矩阵的主对角线元素
		np.linalg.eig(arr) 特征根与特征向量
		np.linalg.solve(arr)  多元线性方程组的求解
		
	5 伪随机数的生成
		常用的随机分布函数（了解）