---
title: 'Gewusst wie: Verwenden der ScrollViewer-Bildlaufmethoden'
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
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc9b79ae9b8078bbdc4c41fb0c952237f86fcac8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>Gewusst wie: Verwenden der ScrollViewer-Bildlaufmethoden
In diesem Beispiel wird gezeigt, wie das Durchführen eines Bildlaufs Methoden der der <xref:System.Windows.Controls.ScrollViewer> Element. Diese Methoden bieten inkrementelle Durchführen eines Bildlaufs von Inhalten, die entweder nach Zeile oder Seite, in einem <xref:System.Windows.Controls.ScrollViewer>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ScrollViewer> mit dem Namen `sv1`, das ein untergeordnetes Element hostet <xref:System.Windows.Controls.TextBlock> Element. Da die <xref:System.Windows.Controls.TextBlock> ist größer als das übergeordnete Element <xref:System.Windows.Controls.ScrollViewer>, Bildlaufleisten angezeigt werden, um einen Bildlauf zu aktivieren. <xref:System.Windows.Controls.Button>Elemente, die die verschiedenen Durchführen eines Bildlaufs Methoden darstellen, die auf der linken Seite in einer separaten angedockt sind <xref:System.Windows.Controls.StackPanel>. Jede <xref:System.Windows.Controls.Button> in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei eine verwandte benutzerdefinierte Methode aufruft, die in Scrollverhalten steuert <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> und <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> Methoden.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
