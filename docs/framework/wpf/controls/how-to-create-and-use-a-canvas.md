---
title: 'Gewusst wie: Erstellen und Verwenden eines Canvas'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 562531f75d6a800ff93a02709a053b790de52ea2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-use-a-canvas"></a>Gewusst wie: Erstellen und Verwenden eines Canvas
In diesem Beispiel wird gezeigt, wie zum Erstellen und Verwenden einer Instanz von <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel positioniert zwei explizit <xref:System.Windows.Controls.TextBlock> Elemente mithilfe der <xref:System.Windows.Controls.Canvas.SetTop%2A> und <xref:System.Windows.Controls.Canvas.SetLeft%2A> Methoden der <xref:System.Windows.Controls.Canvas>. Im Beispiel weist auch eine <xref:System.Windows.Controls.Control.Background%2A> Farbe des `LightSteelBlue` auf die <xref:System.Windows.Controls.Canvas>.  
  
> [!NOTE]
>  Bei Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Position <xref:System.Windows.Controls.TextBlock> verwenden Sie die Elemente, die <xref:System.Windows.Controls.Canvas.Top%2A> und <xref:System.Windows.Controls.Canvas.Left%2A> Eigenschaften.  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.TextBlock>  
 <xref:System.Windows.Controls.Canvas.SetTop%2A>  
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)
