---
title: 如何：继承 Windows 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 275ae52a36ed9766e2569bd6c8ecdea78ea56e0b
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276283"
---
# <a name="how-to-inherit-windows-forms"></a>如何：继承 Windows 窗体
通过从基窗体继承创建新的 Windows 窗体是事半功倍的便捷途径，而每次需要用它时，都无需完全重新创建窗体。  
  
 若要深入了解如何使用“继承选择器”对话框在设计时继承窗体以及如何直观地区分继承控件的安全级别，请参阅[如何：使用“继承选择器”对话框继承窗体](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)。  
  
 **请注意**：为了从窗体进行继承，包含该窗体的文件或命名空间必须生成为可执行文件或 DLL。 若要生成项目，请从“生成”菜单选择“生成”。 此外，对命名空间的引用必须添加到继承窗体的类。 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-inherit-a-form-programmatically"></a>若要以编程方式继承窗体  
  
1.  在类中，添加对命名空间的引用，该命名空间包含想要被继承的窗体。  
  
2.  在类定义中，将引用添加到将被继承的窗体。 引用应包括包含窗体的命名空间，后跟一个句点，然后是基本窗体本身的名称。  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 当继承窗体时，请记住，由于每个事件是由基类和继承类一起进行处理的，所以事件处理程序被调用两次时可能会出现问题。 若要深入了解如何避免此问题，请参阅[有关 Visual Basic 中继承的事件处理程序的疑难解答](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)。  
  
## <a name="see-also"></a>请参阅  
 [Inherits 语句](~/docs/visual-basic/language-reference/statements/inherits-statement.md)  
 [Imports 语句（.NET 命名空间和类型）](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [using](~/docs/csharp/language-reference/keywords/using.md)  
 [修改基窗体的外观的效果](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 [Windows 窗体可视化继承](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
