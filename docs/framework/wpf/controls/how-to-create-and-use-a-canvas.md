---
title: 'Vorgehensweise: Erstellen und Verwenden eines Canvas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: d2d56851de2444ce246750688df67ed5ba9adb9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687478"
---
# <a name="how-to-create-and-use-a-canvas"></a>Vorgehensweise: Erstellen und Verwenden eines Canvas
Dieses Beispiel zeigt das Erstellen und verwenden Sie eine Instanz des <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird explizit positioniert, zwei <xref:System.Windows.Controls.TextBlock> Elemente mithilfe der <xref:System.Windows.Controls.Canvas.SetTop%2A> und <xref:System.Windows.Controls.Canvas.SetLeft%2A> Methoden <xref:System.Windows.Controls.Canvas>. Im Beispiel weist auch eine <xref:System.Windows.Controls.Control.Background%2A> Farbe des `LightSteelBlue` auf die <xref:System.Windows.Controls.Canvas>.  
  
> [!NOTE]
>  Bei Verwendung von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] an Position <xref:System.Windows.Controls.TextBlock> Elemente verwenden, die <xref:System.Windows.Controls.Canvas.Top%2A> und <xref:System.Windows.Controls.Canvas.Left%2A> Eigenschaften.  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)
