/*
	主页加载方法
*/
//系统时间显示
setInterval("document.getElementById('nowTime').innerHTML=new Date().toLocaleString()+' 星期'+'日一二三四五六'.charAt(new Date().getDay());", 1000);
var setting = {
    data: {
        simpleData: {
            enable: true
        }
    },
    view: {
        selectedMulti: false
    },
    callback: {
        onClick: function (e, id, node) {
            var zTree = $.fn.zTree.getZTreeObj("menuTree");
            if (node.isParent) {
                zTree.expandNode();
            } else {
                addTabs(node.name, node.file);
            }
        }
    }
};

var zNodes = [
	{ id: 1, pId: 0, name: "系统管理", open: true },
	{ id: 11, pId: 1, name: "用户管理", file: "user/user.html" },
	{ id: 12, pId: 1, name: "数据备份", file: "backup.html" },
	{ id: 13, pId: 1, name: "权限管理", file: "authority.html" },
	{ id: 14, pId: 1, name: "角色管理", file: "role.html" },

    { id: 2, pId: 0, name: "公用资料", open: true },
	{ id: 21, pId: 2, name: "仓库", file: "../XS_pxg/仓库设定.html" },
    { id: 3, pId: 2, name: "部门", file: "../XS_pxg/部门设定.html" },
	{ id: 22, pId: 2, name: "物料类别", file: "../CG_xjj/物料类别.html" },
	{ id: 23, pId: 2, name: "物料主文件", file: "" },
    //{ id: 24, pId: 2, name: "客户类别", file: "../CG_xjj/采购.html" },
    { id: 25, pId: 2, name: "客户类别", file: "../XS_lgw/Khlb.html" },
	//{ id: 26, pId: 2, name: "潜在客户主文件", file: "" },
    { id: 27, pId: 2, name: "客户主文件", file: "../XS_lgw/KhZwj.HTML" },
    { id: 28, pId: 2, name: "供应商类别", file: "../CG_xjj/供应商类别.html" },
    { id: 29, pId: 2, name: "供应商主文件", file: "../CG_ljm/gongyingshangzhuwenjian.html" },
    { id: 19, pId: 2, name: "计量单位", file: "../CG_xjj/计量单位.html" },
    { id: 18, pId: 2, name: "人员主文件", file: "../XS_pxg/人员.html" },

	{ id: 3, pId: 0, name: "采购管理", open: true },
	{ id: 30, pId: 3, name: "采购请购单", file: "../CG_xz/采购请购.html" },
	{ id: 31, pId: 3, name: "采购询价单", file: "../CG_xz/采购询价.html" },
	{ id: 32, pId: 3, name: "采购订单", file: "../CG_ysl/Index.html" },
    { id: 33, pId: 3, name: "采购入库单", file: "../CG_xjj/采购入库单.html" },
	{ id: 34, pId: 3, name: "采购退货单", file: "../CG_ljm/caigoutuihuo.html" },

    { id: 4, pId: 0, name: "销售管理", open: true },
	{ id: 40, pId: 4, name: "销售报价单", file: "../XS_hp/xiaoshoubaojia.html" },
	{ id: 41, pId: 4, name: "销售订单", file: "../XS_hp/xiaoshoudd.html" },
	{ id: 42, pId: 4, name: "销售出库单", file: "../XS_lgw/Xsck.HTML" },
    { id: 43, pId: 4, name: "销售退货单", file: "../XS_pxg/退货.html" },

    { id: 5, pId: 0, name: "库存管理", open: true },
	{ id: 50, pId: 5, name: "调拨单", file: "" },
	{ id: 51, pId: 5, name: "盘点单", file: "../CG_ysl/Show.html" },
	{ id: 52, pId: 5, name: "调价单", file: "" },

    { id: 6, pId: 0, name: "账款管理", open: true },
	{ id: 60, pId: 6, name: "预收款单", file: "../XS_xjf/yskd.html" },
	{ id: 61, pId: 6, name: "收款冲款单", file: "../XS_xjf/skckd.html" },
	{ id: 62, pId: 6, name: "预付款单", file: "../CG_wpj/预付款单.html" },
    { id: 62, pId: 6, name: "付款冲款单", file: "../CG_wpj/应付冲款单.html" },
];

$(function () {
    $.fn.zTree.init($("#menuTree"), setting, zNodes);
    var zTree = $.fn.zTree.getZTreeObj("menuTree");

    //中间部分tab
    $('#tabs').tabs({
        border: false,
        fit: true,
        onSelect: function (title, index) {
            var treeNode = zTree.getNodeByParam("name", title, null);
            zTree.selectNode(treeNode);
        }
    });

    $('.index_panel').panel({
        width: 300,
        height: 200,
        closable: true,
        minimizable: true,
        title: 'My Panel'
    });

});

//添加一个选项卡面板 
function addTabs(title, url, icon) {
    if (!$('#tabs').tabs('exists', title)) {
        $('#tabs').tabs('add', {
            title: title,
            content: '<iframe src="' + url + '" frameBorder="0" border="0" scrolling="no" style="width: 100%; height: 100%;"/>',
            closable: true
        });
    } else {
        $('#tabs').tabs('select', title);
    }
}