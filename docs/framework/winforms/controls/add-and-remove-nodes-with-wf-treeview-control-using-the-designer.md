---
title: 如何：使用设计器用 Windows 窗体 TreeView 控件添加和移除节点
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 95f3f097d8e01828f2727bac742c752b656019e5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211874"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>如何：使用设计器用 Windows 窗体 TreeView 控件添加和移除节点
因为 Windows 窗体<xref:System.Windows.Forms.TreeView>控件以分层方式，添加您必须特别注意到其父节点是节点时将显示节点。  
  
 下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.TreeView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)并[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a>若要添加或删除在设计器中的节点  
  
1.  选择 <xref:System.Windows.Forms.TreeView> 控件。  
  
2.  在中**属性**窗口中，单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮旁边<xref:System.Windows.Forms.TreeView.Nodes%2A>属性。  
  
     **树节点编辑器**出现。  
  
3.  若要将节点添加，必须存在的根节点;如果不存在，首先必须通过单击添加根**添加根**按钮。 然后可以通过选择根节点或任何其他节点并单击添加子节点**添加子项**按钮。  
  
4.  若要删除节点，请选择节点以删除，然后单击**删除**按钮。  
  
## <a name="see-also"></a>请参阅  
 [TreeView 控件](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [TreeView 控件概述](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [如何：设置 Windows 窗体 TreeView 控件的图标](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [如何：循环访问 Windows 窗体 TreeView 控件的所有节点](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [如何：确定哪个 TreeView 节点获得了单击](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
