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
ms.openlocfilehash: d458d87586614093b35fcd73969dea04fe620351
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543009"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>Gewusst wie: Erstellen eines Rollovereffekts mit Ereignissen
In diesem Beispiel wird gezeigt, wie die Farbe eines Elements ändern, wie der Mauszeiger die Form eintritt und diese verlässt des Bereichs, der vom Element eingenommene wird.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine Code-Behind-Datei.  
  
> [!NOTE]
>  In diesem Beispiel wird veranschaulicht, wie Ereignisse, aber die empfohlene Methode, um diesen Effekt zu erreichen ist die Verwendung einer <xref:System.Windows.Trigger> in einem Format. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche, die sich aus <xref:System.Windows.Controls.Border> um eine <xref:System.Windows.Controls.TextBlock>, und fügt die <xref:System.Windows.Input.Mouse.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> Ereignishandler an das <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Der folgende Code-behind erstellt die <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave> -Ereignishandler.  Wenn der Mauszeiger wird die <xref:System.Windows.Controls.Border>, den Hintergrund der <xref:System.Windows.Controls.Border> in Rot geändert wird.  Wenn der Mauszeiger die Form verlässt die <xref:System.Windows.Controls.Border>, den Hintergrund der <xref:System.Windows.Controls.Border> nicht wieder in Weiß geändert wird.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
