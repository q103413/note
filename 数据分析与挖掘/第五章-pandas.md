

01 序列与数据框的介绍	序列Series：
		是一种存储数据的容器，类似于一维数组，要求序列中的元素具有相同的数据类型。
		可以将其理解为数据集中的一个字段（列）。
	数据框DataFrame：
		同样是存储数据的容器，类似于二维数组，所不同的是，数据框中的每一列可以是不同的数据类型。
		数据框实际上是由多个序列组合而成的。

	序列构造的方法
		pd.Series()
	
	数据框构造的方法
		pd.DataFrame()
		
	外部数据的读取
		pd.read_table() 读取txt或者csv格式
		
		pd.read_csv()	读取表格csv格式
		
		pd.read_excel()	读取电子表格Excel格式
	
	数据库数据的读取
		# 连接MySQL		con = pymysql.connect(host=None, user=None, password=‘’,=None, port=0,  charset=‘’)
		#读取数据框
		result = pd.read_sql(sql, con)				
		#关闭数据框
		con.close

数据的清洗
	数据类型的转换
		astype('数据类型')				 对于数值型、字符型、布尔型等类型的转换可以使用astype方法；	
		to_datetime('列名变量'，'当前日期格式') 		对于日期时间型的转换需使用to_datetime函数；
		
	描述性统计
		decripe()	默认统计数值型变量
		decripe(include='object')	默认统计离散型型变量
	
	重复观察的识别与处理
		duplicated 			用于重复观测的识别
		drop_duplicates 	删除重复项
		
	缺失值的识别与处理
		isnull							用于缺失观测的识别
		notnull							isnull的反函数
		dropna							删除缺失
			drop('列名/行名',axis)			变量删除
				drop函数基本介绍：
				功能：删除数据集中多余的数据
				DataFrame.drop(labels=None, axis=0)
				常用参数详解：
				labels:待删除的行名or列名； 
				axis:删除时所参考的轴，0为行，1为列； 
			del data['列名']
				
		fillna()					填补缺失（常数替换、前/后向替换、统计值替换）	  
			统计值替换 
				离散型：众数
				数值型：平均值、中位数
				
	    异常值的识别与处理
			1、n个标准差法
				
			2、箱线图判别法
			
		
数据子集的筛选
			你应该根据你的索引类型使用：
			iloc 	位置整数
					通过行号和列号进行数据的筛选，索引是int型，前闭后开。
					iloc[a:b,c:d]:取行索引从a到b-1，列索引从c到d-1的数据。
					
			loc		标签
					具体的行标签（或条件表达式）和列标签（字段名）
					定位行列：data.loc[行索引, 列名]  或者	data.loc[where条件] 
					使用loc函数，索引的是字符串，前后都要取，是属于“前闭后闭”的情况。
					
			# ix		iloc和loc的混合
			
			将一个或者多个列用作行标签（行索引）			df.set_index('colums')
			
			NumpyPy的通用函数对pandas对象也生效。比如np.abs()、np.mean()等等
			apply(f,axis)	方法可以实现将函数f应用到每一行或每一列上。
				# 每列调用一次f方法
				df.apply(f)
				# 每行调用一次f方法
				df.apply(f, axis='columns')

数据的合并与连接(多个pandas对象)
	数据的合并
		pd.concat

	数据的连接
		pd.merge
	
	reset_index	重置索引，并使用默认索引,inplace：bool, default False。修改数据帧（不要创建新对象）

数据的汇总
	透视表
		pd.pivot_table(index='',columns='',values='')
		
	数据库中的分组统计
		
	Python中的分组汇总
		groupby“方法”：用于汇总前，设定被分组的变量
		ggg(aggregate)“方法”：可基于groupby的结果做进一步的统计汇总


	