---
title: 'Vorgehensweise: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: 6605a6a56fba587678227f5826982ec3266b153c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356292"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Vorgehensweise: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel
Dieses Beispiel zeigt, wie Sie Anpassen der <xref:System.Windows.Controls.StackPanel.Orientation%2A> des Inhalts in einer <xref:System.Windows.Controls.StackPanel> -Element sowie Gewusst wie: Anpassen der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> von untergeordnetem Inhalt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt drei <xref:System.Windows.Controls.ListBox> Elemente im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Jede <xref:System.Windows.Controls.ListBox> stellt die möglichen Werte der <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaften eine <xref:System.Windows.Controls.StackPanel>. Wenn ein Benutzer einen Wert in einem der auswählt der <xref:System.Windows.Controls.ListBox> Elemente, die zugeordnete Eigenschaft die <xref:System.Windows.Controls.StackPanel> und ihre untergeordneten <xref:System.Windows.Controls.Button> Elemente ändern.  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Der folgende Code-Behind-Datei definiert die Ereignisse, die zugeordnet werden die Änderungen der <xref:System.Windows.Controls.ListBox> Änderungen der Auswahl. <xref:System.Windows.Controls.StackPanel> wird durch identifiziert die <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [Übersicht über Panel-Elemente](panels-overview.md)
