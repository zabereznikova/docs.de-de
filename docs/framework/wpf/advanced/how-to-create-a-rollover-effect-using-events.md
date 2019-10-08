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
ms.openlocfilehash: 806056397200fa5c567e83227499ba721544f523
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005180"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Vorgehensweise: Erstellen eines Rollovereffekts mit Ereignissen
Dieses Beispiel zeigt, wie Sie die Farbe eines Elements ändern können, wenn der Mauszeiger in den Bereich wechselt, der vom-Element belegt wird.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Datei und einer Code Behind-Datei.  
  
> [!NOTE]
> In diesem Beispiel wird veranschaulicht, wie Ereignisse verwendet werden, aber die empfohlene Vorgehensweise zum Erreichen desselben Effekts ist die Verwendung einer <xref:System.Windows.Trigger> in einem Stil. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code erstellt die Benutzeroberfläche, die aus <xref:System.Windows.Controls.Border> um einen <xref:System.Windows.Controls.TextBlock> besteht und die <xref:System.Windows.Input.Mouse.MouseEnter>-und <xref:System.Windows.UIElement.MouseLeave>-Ereignishandler an den <xref:System.Windows.Controls.Border> anfügt.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Der folgende Code Behind erstellt die Ereignishandler <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave>.  Wenn der Mauszeiger in den <xref:System.Windows.Controls.Border> eintritt, wird der Hintergrund des <xref:System.Windows.Controls.Border> in rot geändert.  Wenn der Mauszeiger den <xref:System.Windows.Controls.Border> verlässt, wird der Hintergrund des <xref:System.Windows.Controls.Border> wieder in weiß geändert.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
