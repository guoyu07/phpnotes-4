#ThinkPHP的Page分页
`thinkphp` `分页`

- - -

###为什么ThinkPHP的Page分页类不显示header信息？
处理:
```php
$Page->setConfig('theme',"%HEADER% %FIRST% %UP_PAGE% %LINK_PAGE% %DOWN_PAGE% %END%");
```
所有代码
```php
	     //分页:
		//获得总条数
		$count=$shangpingModel->getAllCount($id);
		//每页显示两条
		$Page = new \Think\Page($count,2);
		$Page->setConfig('prev','上页');	
		$Page->setConfig('next','下页');
		$Page->setConfig('first','首页');
		$Page->setConfig('first','首页');
		$Page->setConfig('last','尾页');
	    $Page->setConfig('theme',"%HEADER% %FIRST% %UP_PAGE% %LINK_PAGE% %DOWN_PAGE% %END%");
		$Page->setConfig('header',"共 %TOTAL_ROW% 条记录");
		$show       = $Page->show();// 分页显示输出
		//获得数据
		$list = $shangpingModel->where("isShanghu={$id}")->limit($Page->firstRow.','.$Page->listRows)->select();
		$this->assign('shanghuInfo',$result2);//其他一些必数据,和分页无关
		$this->assign('shangpingInfo',$list);// 赋值数据集
		$this->assign('shanghuiName',$shanghuiName);
		$this->assign('page',$show);// 赋值分页输出
		$this->display(shangping); // 输出模板
```