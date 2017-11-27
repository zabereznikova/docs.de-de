---
title: 'Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel'
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
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bccf0455c736d14bd77113841603022d4c362787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel
In diesem Beispiel wird gezeigt, wie zum Anpassen der <xref:System.Windows.Controls.StackPanel.Orientation%2A> von Inhalten innerhalb einer <xref:System.Windows.Controls.StackPanel> Element sowie zum Anpassen der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> von untergeordnetem Inhalt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt drei <xref:System.Windows.Controls.ListBox> Elemente im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Jede <xref:System.Windows.Controls.ListBox> stellt die möglichen Werte für die <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaften eine <xref:System.Windows.Controls.StackPanel>. Wenn ein Benutzer einen Wert in einem der auswählt der <xref:System.Windows.Controls.ListBox> Elemente, die zugeordnete Eigenschaft von der <xref:System.Windows.Controls.StackPanel> und seiner untergeordneten <xref:System.Windows.Controls.Button> Elemente ändern.  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Der folgende Code-Behind-Datei definiert die Änderungen auf die Ereignisse, die zugeordnet sind die <xref:System.Windows.Controls.ListBox> Menüauswahl ändert. <xref:System.Windows.Controls.StackPanel>wird durch identifiziert die <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
