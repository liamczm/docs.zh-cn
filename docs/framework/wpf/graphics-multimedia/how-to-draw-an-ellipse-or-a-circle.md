---
title: 如何：绘制椭圆或圆
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: ddeada8619d1b6c8970f1efb7cca1bc98773d0c5
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262069"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>如何：绘制椭圆或圆
此示例演示如何使用来绘制椭圆和圆<xref:System.Windows.Shapes.Ellipse>元素。 若要绘制一个椭圆，创建<xref:System.Windows.Shapes.Ellipse>元素，并指定其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>。 使用其<xref:System.Windows.Shapes.Shape.Fill%2A>属性来指定<xref:System.Windows.Media.Brush>用来绘制椭圆形的内部。 使用其<xref:System.Windows.Shapes.Shape.Stroke%2A>属性来指定<xref:System.Windows.Media.Brush>用于绘制椭圆的边框。 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>属性指定的椭圆边框粗细。  
  
 若要绘制一个圆圈，确保<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>的<xref:System.Windows.Shapes.Ellipse>相等的元素。  
  
 下面的示例绘制四<xref:System.Windows.Shapes.Ellipse>中的元素<xref:System.Windows.Controls.Canvas>。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 虽然此示例使用<xref:System.Windows.Controls.Canvas>来包含省略号，但是您可以使用 ellipse 元素 （和所有其他形状元素） 以及任何<xref:System.Windows.Controls.Panel>或<xref:System.Windows.Controls.Control>支持非文本内容。  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)
