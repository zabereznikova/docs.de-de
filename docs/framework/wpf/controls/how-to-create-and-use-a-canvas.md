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
ms.openlocfilehash: edef660b2da2f09e0a6edbc0a87f0d1f26eb03da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964220"
---
# <a name="how-to-create-and-use-a-canvas"></a>Vorgehensweise: Erstellen und Verwenden eines Canvas
In diesem Beispiel wird gezeigt, wie eine Instanz von <xref:System.Windows.Controls.Canvas>erstellt und verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden <xref:System.Windows.Controls.TextBlock> Beispiel werden zwei-Elemente explizit mithilfe der <xref:System.Windows.Controls.Canvas.SetTop%2A> -Methode und der- <xref:System.Windows.Controls.Canvas.SetLeft%2A> Methode von <xref:System.Windows.Controls.Canvas>positioniert. Im Beispiel wird auch eine <xref:System.Windows.Controls.Control.Background%2A> Farbe von `LightSteelBlue` <xref:System.Windows.Controls.Canvas>zugewiesen.  
  
> [!NOTE]
> Wenn Sie zum [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] positionieren <xref:System.Windows.Controls.TextBlock> von Elementen verwenden, verwenden <xref:System.Windows.Controls.Canvas.Top%2A> Sie <xref:System.Windows.Controls.Canvas.Left%2A> die-Eigenschaft und die-Eigenschaft.  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Themen zu Vorgehensweisen](canvas-how-to-topics.md)
