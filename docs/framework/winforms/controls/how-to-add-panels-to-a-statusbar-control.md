---
title: 如何：向 StatusBar 控件添加面板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- panels [Windows Forms], status bars
- status bars [Windows Forms], adding panels
- StatusBar control [Windows Forms], adding panels
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
ms.openlocfilehash: dd006f669ab6f0186bbcc7d1c76f9852ab6e8f60
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44189204"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a>如何：向 StatusBar 控件添加面板
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip>并<xref:System.Windows.Forms.ToolStripStatusLabel>控件替换，并将功能添加到<xref:System.Windows.Forms.StatusBar>并<xref:System.Windows.Forms.StatusBarPanel>控制; 但是，<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控件将保留用于向后兼容性并供将来使用，如果你选择。  
  
 中的可编程区域[StatusBar 控件](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md)控件由实例构成<xref:System.Windows.Forms.StatusBarPanel>类。 通过添加到添加这些<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>类。  
  
### <a name="to-add-panels-to-a-status-bar"></a>若要添加到状态栏面板  
  
1.  在过程中，通过将它们添加到创建状态栏面板<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>。 指定属性设置为通过其索引的各个面板传递<xref:System.Windows.Forms.StatusBar.Panels%2A>属性。  
  
     在下面的代码示例中，将路径设置图标的位置是**我的文档**文件夹。 使用此位置是因为您可以假定大多数运行 Windows 操作系统的计算机将包含该文件夹。 选择此位置还允许具有最少的系统访问级别的用户安全地运行应用程序。 下面的示例要求具有的窗体<xref:System.Windows.Forms.StatusBar>已添加的控件。  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>是从零开始的集合，因此代码应进行相应处理。  
  
    ```vb  
    Public Sub CreateStatusBarPanels()  
    ' Create panels and set text property.  
       StatusBar1.Panels.Add("One")  
       StatusBar1.Panels.Add("Two")  
       StatusBar1.Panels.Add("Three")  
    ' Set properties of StatusBar panels.  
    ' Set AutoSize property of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(1).AutoSize = StatusBarPanelAutoSize.Contents  
       StatusBar1.Panels(2).AutoSize = StatusBarPanelAutoSize.Contents  
    ' Set BorderStyle property of panels.  
       StatusBar1.Panels(0).BorderStyle = StatusBarPanelBorderStyle.Raised  
       StatusBar1.Panels(1).BorderStyle = StatusBarPanelBorderStyle.Sunken  
       StatusBar1.Panels(2).BorderStyle = StatusBarPanelBorderStyle.Raised  
    ' Set Icon property of third panel. You should replace the bolded  
    ' icon in the sample below with an icon of your own choosing.  
       StatusBar1.Panels(2).Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
       StatusBar1.ShowPanels = True  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateStatusBarPanels()  
    {  
       // Create panels and set text property.  
       statusBar1.Panels.Add("One");  
       statusBar1.Panels.Add("Two");  
       statusBar1.Panels.Add("Three");  
       // Set properties of StatusBar panels.  
       // Set AutoSize property of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[1].AutoSize = StatusBarPanelAutoSize.Contents;  
       statusBar1.Panels[2].AutoSize = StatusBarPanelAutoSize.Contents;  
       // Set BorderStyle property of panels.  
       statusBar1.Panels[0].BorderStyle =  
          StatusBarPanelBorderStyle.Raised;  
       statusBar1.Panels[1].BorderStyle = StatusBarPanelBorderStyle.Sunken;  
       statusBar1.Panels[2].BorderStyle = StatusBarPanelBorderStyle.Raised;  
       // Set Icon property of third panel. You should replace the bolded  
       // icon in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       statusBar1.Panels[2].Icon =   
          new System.Drawing.Icon (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Icon.ico");  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateStatusBarPanels()  
       {  
          // Create panels and set text property.  
          statusBar1->Panels->Add("One");  
          statusBar1->Panels->Add("Two");  
          statusBar1->Panels->Add("Three");  
          // Set properties of StatusBar panels.  
          // Set AutoSize property of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[1]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          statusBar1->Panels[2]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          // Set BorderStyle property of panels.  
          statusBar1->Panels[0]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          statusBar1->Panels[1]->BorderStyle =  
             StatusBarPanelBorderStyle::Sunken;  
          statusBar1->Panels[2]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          // Set Icon property of third panel.  
          // You should replace the bolded image   
          // in the sample below with an icon of your own choosing.  
          statusBar1->Panels[2]->Icon =  
             gcnew System::Drawing::Icon(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Icon.ico"));  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [集合编辑器对话框](https://msdn.microsoft.com/library/53fb3aad-bffa-4da5-ac89-8438e6fc803c)  
 [如何：设置状态栏面板的大小](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [演练：在运行时更新状态栏信息](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [如何：确定 Windows 窗体 StatusBar 控件中的哪个面板获得了单击](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [StatusBar 控件概述](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
