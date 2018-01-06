# easyui-edatagrid
使用edatagrid扩展开启表单数据编辑的功能   

需要导入扩展 jquery.edatagrid.js扩展还有jquery和easyui的js  

开始表单编辑功能  

field 设置editor={}---设置文本类型  


//设置访问路径
$('#tt').edatagrid({
	url: 'datagrid_data.json',
	saveUrl: ...,
	updateUrl: ...,
	destroyUrl: ...
});


会自动访问链接，并且提供该行的所有参数


注意=========================================  
php端必须返回值包含isError才能识别

echo json_encode(array(
	'isError' => true,
	'msg' => 'error message.'
));

===========================================   
js设置捕捉报错信息
$('#dg').edatagrid({
	onError: function(index,row){
		alert(row.msg);
	}
});
