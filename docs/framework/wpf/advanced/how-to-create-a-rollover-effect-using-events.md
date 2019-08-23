---
title: 'Vorgehensweise: Erstellen eines Rollovereffekts mit Ereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960384"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Vorgehensweise: Erstellen eines Rollovereffekts mit Ereignissen
Dieses Beispiel zeigt, wie Sie die Farbe eines Elements ändern können, wenn der Mauszeiger in den Bereich wechselt, der vom-Element belegt wird.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei und einer Code Behind-Datei.  
  
> [!NOTE]
> In diesem Beispiel wird veranschaulicht, wie Ereignisse verwendet werden, aber die empfohlene Vorgehensweise zum Erreichen desselben Effekts ist <xref:System.Windows.Trigger> die Verwendung von in einem Stil. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] wird die Benutzeroberfläche erstellt, die <xref:System.Windows.Controls.Border> aus einem <xref:System.Windows.Controls.TextBlock>besteht, und die <xref:System.Windows.Input.Mouse.MouseEnter> Ereignishandler <xref:System.Windows.UIElement.MouseLeave> und an den <xref:System.Windows.Controls.Border>anfügt.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Der folgende Code Behind erstellt die <xref:System.Windows.UIElement.MouseEnter> Ereignis <xref:System.Windows.UIElement.MouseLeave> Handler und.  Wenn der Mauszeiger in den <xref:System.Windows.Controls.Border>eintritt, <xref:System.Windows.Controls.Border> wird der Hintergrund der in rot geändert.  Wenn der Mauszeiger das <xref:System.Windows.Controls.Border>-Zeichen verlässt, <xref:System.Windows.Controls.Border> wird der Hintergrund von wieder in weiß geändert.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
