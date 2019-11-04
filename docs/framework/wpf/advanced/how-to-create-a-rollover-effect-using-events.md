---
title: 'Gewusst wie: Erstellen eines Rollovereffekts mit Ereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: ccdc8aeb26b538814b2f9020e1e3a5b311fa5a99
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460156"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Gewusst wie: Erstellen eines Rollovereffekts mit Ereignissen
Dieses Beispiel zeigt, wie Sie die Farbe eines Elements ändern können, wenn der Mauszeiger in den Bereich wechselt, der vom-Element belegt wird.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Datei und einer Code Behind-Datei.  
  
> [!NOTE]
> In diesem Beispiel wird veranschaulicht, wie Ereignisse verwendet werden, aber die empfohlene Vorgehensweise zum Erreichen desselben Effekts ist die Verwendung einer <xref:System.Windows.Trigger> in einem Stil. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code erstellt die Benutzeroberfläche, die aus <xref:System.Windows.Controls.Border> um eine <xref:System.Windows.Controls.TextBlock>besteht, und fügt die <xref:System.Windows.Input.Mouse.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> Ereignishandler an den <xref:System.Windows.Controls.Border>an.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Der folgende Code Behind erstellt die <xref:System.Windows.UIElement.MouseEnter>-und <xref:System.Windows.UIElement.MouseLeave>-Ereignishandler.  Wenn der Mauszeiger in den <xref:System.Windows.Controls.Border>eintritt, wird der Hintergrund des <xref:System.Windows.Controls.Border> in rot geändert.  Wenn der Mauszeiger den <xref:System.Windows.Controls.Border>verlässt, wird der Hintergrund des <xref:System.Windows.Controls.Border> wieder in weiß geändert.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
