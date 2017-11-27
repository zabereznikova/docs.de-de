---
title: "Gewusst wie: Durchführen eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle"
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
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1895507c30ad5267d4c2b1afff3acf004e872d40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>Gewusst wie: Durchführen eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle
In diesem Beispiel wird gezeigt, wie einen Bildlauf im Inhalt mithilfe der <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Funktionen des die <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle. Das Beispiel erstellt eine <xref:System.Windows.Controls.StackPanel> Element im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , die in ein übergeordnetes Element geschachtelt ist <xref:System.Windows.Controls.ScrollViewer>. Die untergeordneten Elemente des der <xref:System.Windows.Controls.StackPanel> können mithilfe von definierten Methoden logisch gescrollt werden die <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle und die Umwandlung in der Instanz von <xref:System.Windows.Controls.StackPanel> (`sp1`) im Code.  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Jede <xref:System.Windows.Controls.Button> in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei löst eine zugeordnete benutzerdefinierte Methode, die in Scrollverhalten steuert <xref:System.Windows.Controls.StackPanel>. Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> -Methoden auch generisch wird gezeigt, wie die Positionierung Methoden verwenden, die die <xref:System.Windows.Controls.Primitives.IScrollInfo> Klasse definiert.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 <xref:System.Windows.Controls.StackPanel>  
 [Übersicht über ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
