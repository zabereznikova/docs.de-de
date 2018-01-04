---
title: "Gewusst wie: Ändern des Endes einer Zeile oder eines Segments"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d2cd55de403b766344749259068ccd313558f89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Gewusst wie: Ändern des Endes einer Zeile oder eines Segments
In diesem Beispiel wird gezeigt, wie so ändern Sie die Form am Anfang oder Ende eines offenen <xref:System.Windows.Shapes.Shape> Element. So ändern Sie die Abdeckung am Anfang eines geöffneten <xref:System.Windows.Shapes.Shape>, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> Eigenschaft. So ändern Sie die Abdeckung am Ende eines geöffneten <xref:System.Windows.Shapes.Shape>, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> Eigenschaft. Um die verfügbaren Zeilenenden finden Sie unter der <xref:System.Windows.Media.PenLineCap> Enumeration.  
  
> [!NOTE]
>  Diese Eigenschaft wirkt sich nur auf eine offene Form, wie z. B. eine <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, oder ein offenes <xref:System.Windows.Shapes.Path> Element.  
  
 Im folgende Beispiel zeichnet vier <xref:System.Windows.Shapes.Polyline> Elemente und einen anderen Satz von Shapes an den Enden der einzelnen verwendet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
