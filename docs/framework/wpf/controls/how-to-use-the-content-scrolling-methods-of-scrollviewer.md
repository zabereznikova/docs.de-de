---
title: 'Vorgehensweise: Verwenden der ScrollViewer-Bildlaufmethoden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: e81c63de16d09de8435d5ec49a013bf8dc5927cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697303"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>Vorgehensweise: Verwenden der ScrollViewer-Bildlaufmethoden
Dieses Beispiel zeigt, wie Sie mit der Bildlaufmethoden des der <xref:System.Windows.Controls.ScrollViewer> Element. Diese Methoden bieten inkrementellen Bildlauf in Inhalten, indem Zeile oder Seite einem <xref:System.Windows.Controls.ScrollViewer>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ScrollViewer> mit dem Namen `sv1`, das ein untergeordnetes Element hostet <xref:System.Windows.Controls.TextBlock> Element. Da die <xref:System.Windows.Controls.TextBlock> ist größer als das übergeordnete Element <xref:System.Windows.Controls.ScrollViewer>, Bildlaufleisten angezeigt werden, um einen Bildlauf zu aktivieren. <xref:System.Windows.Controls.Button> Elemente, die die verschiedenen Bildlaufmethoden darstellen, die auf der linken Seite in einem separaten angedockt sind <xref:System.Windows.Controls.StackPanel>. Jede <xref:System.Windows.Controls.Button> in die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei ruft eine zugeordnete benutzerdefinierte Methode, die in Scrollverhalten steuert <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xaml[ScrollViewerMethods#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> und <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> Methoden.  
  
 [!code-csharp[ScrollViewerMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.StackPanel>
