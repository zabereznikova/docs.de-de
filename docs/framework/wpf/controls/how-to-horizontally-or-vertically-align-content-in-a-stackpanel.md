---
title: 'Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel'
description: Erfahren Sie, wie Sie die Inhalts Orientierung in einem Windows Presentation Foundation StackPanel und HorizontalAlignment und VerticalAlignment von untergeordnetem Inhalt anpassen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: d3c7215d8193d1d8a72597c44cf265f5bd400ea1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167634"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel
In diesem Beispiel wird gezeigt, wie der <xref:System.Windows.Controls.StackPanel.Orientation%2A> Inhalt in einem- <xref:System.Windows.Controls.StackPanel> Element angepasst wird und wie der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> der untergeordnete Inhalt angepasst werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden drei <xref:System.Windows.Controls.ListBox> Elemente in erstellt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Jede <xref:System.Windows.Controls.ListBox> stellt die möglichen Werte der <xref:System.Windows.Controls.StackPanel.Orientation%2A> -Eigenschaft, der-Eigenschaft <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und der-Eigenschaft <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> eines dar <xref:System.Windows.Controls.StackPanel> . Wenn ein Benutzer in einem der-Elemente einen Wert auswählt <xref:System.Windows.Controls.ListBox> , ändern sich die zugeordnete-Eigenschaft der und der untergeordneten <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.Button> Elemente.  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Mit der folgenden Code Behind-Datei werden die Änderungen an den Ereignissen definiert, die mit den <xref:System.Windows.Controls.ListBox> Auswahl Änderungen verknüpft sind. <xref:System.Windows.Controls.StackPanel>wird vom identifiziert <xref:System.Windows.FrameworkElement.Name%2A> `sp1` .  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [Übersicht über Panel-Elemente](panels-overview.md)
