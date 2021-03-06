---
title: "如何：将文本绘制到控件的背景上"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f0c98422e337678e68a8e4b72979635e8c867b4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-to-a-control39s-background"></a>如何：将文本绘制到控件的背景上
通过将文本字符串转换，可以直接到控件的背景绘制文本<xref:System.Windows.Media.FormattedText>对象，并在其中绘制对象到控件的<xref:System.Windows.Media.DrawingContext>。 你也可以使用此方法，从派生的对象的背景的绘制的<xref:System.Windows.Controls.Panel>，如<xref:System.Windows.Controls.Canvas>和<xref:System.Windows.Controls.StackPanel>。  
  
 ![控件文本作为背景显示](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
具有自定义文本背景的控件的示例  
  
## <a name="example"></a>示例  
 若要绘制到控件的背景，创建一个新<xref:System.Windows.Media.DrawingBrush>对象，并绘制对象的已转换的文本<xref:System.Windows.Media.DrawingContext>。 然后，将分配新<xref:System.Windows.Media.DrawingBrush>到控件的背景属性。  
  
 下面的代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象，并绘制到的背景<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Button>对象。  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.FormattedText>  
 [绘制格式化文本](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
